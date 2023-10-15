Node string encoding is all over the place. Let's try to straighten out how it works.

First, some very basics about string encoding. A string is a series of bytes. A byte is 8 bits, each of which can be 0 or 1, so a byte can have 28 or 256 different values. _Encoding_ is the process of squashing the graphics you see on screen, say, 世 - into actual bytes. There are over a million possible Unicode characters - think about all of the different languages and emoji and symbols on the planet.

You could easily represent all of the characters in the Unicode set with an encoding that says simply "assign one number, 4 bytes (or 32 bits) long, for each character in the Unicode set." One 32-bit combo for each character means you can have 4 billion distinct characters. But this would be really inefficient for most documents. For example, the English Bible or dictionary or people's email folders are mostly the characters a-z, A-Z, 0-9, and punctuation. It would be inefficient to waste 4 bytes on every "a" in the document - we want a way to represent it more efficiently.

The most common encoding is [UTF-8](https://en.wikipedia.org/wiki/UTF-8). The main advantage of UTF-8 is that it needs a single byte (instead of four) to encode [Unicode](https://en.wikipedia.org/wiki/Unicode) characters 0-127 - the so-called ASCII set, which includes the ones I listed above. Less common characters are represented with two bytes, and even less common characters with three bytes, and so on.

Because Javascript was invented twenty years ago in the space of ten days, it uses an encoding that uses two bytes to store each character, which translates roughly to an encoding called UCS-2, or another one called [UTF-16](https://en.wikipedia.org/wiki/UTF-16). The letter 'a' is Unicode code point 97, so stored in a Javascript string, the first byte of a UTF-16 code point would be 97 and the second byte would be 0. The euro symbol (`€`) is Unicode code point 8364, so the first byte would be 172 and the second byte would be 32. (The relationship between them: `8364 = (32 << 8) + 172`).

That only gets you Unicode code points 0 through (256*256 = ) 65536, though, so: if the first two-byte character is between 55296 and 56319, it's a [surrogate](https://en.wikipedia.org/wiki/UTF-16#U.2B010000_to_U.2B10FFFF), and you have to read the second two-byte character to figure out what Unicode code point it represents. Javascript will handle this multi-character read for you if you use the new `codePointAt` operator, which can return all Unicode code points, up to 1.1 million. The old `charCodeAt` operator only reads one character at a time (between 0 and 65536) and you'll have to read/decode the second one yourself.

## Where this gets complicated

Because everything else in the world is moving to UTF-8, Node is also trying to move to UTF-8. This gets confusing because Node sometimes asks you to choose which encoding you want, in places where you wouldn't really expect it to ask.

Frequently, you want to convert from a UTF-16 encoded Javascript string to UTF-8 bytes in some form, whether a Buffer or a Uint8Array. Unfortunately Node doesn't offer easy API's to do that; it [buries the conversion logic in C++ code](https://github.com/nodejs/node/blob/master/src/string_bytes.cc#L344), which eventually [calls out to the V8 binary](https://v8.paulfryzel.com/docs/master/classv8_1_1_string.html#aa2529bf836fe251638ebc0a014c1a19c) to handle it.

### Buffers

Node offers [a Buffer type](https://nodejs.org/api/buffer.html), where a Buffer is an array of bytes, and an API, `Buffer.from(string, encoding)`. `encoding` defaults to UTF-8. So far, so good! Unfortunately, sometimes `encoding` refers to the encoding of `string`, and sometimes it refers to the encoding of the bytes in the Buffer.

`Buffer.from('7468697320697320612074c3a97374', 'hex')` will decode the input as a series of hex characters, and store the bytes corresponding to each 2-digit hex character in the Buffer. But in `var a = 'tést'; Buffer.from(a, 'utf8');` the `'utf8'` refers to how the bytes will be _stored_ in the resulting Buffer. Remember, strings are always two bytes per character, so declaring they are `'utf8'` doesn't make sense.

Similarly, the `encoding` parameter in `buf.toString(encoding)` does not refer to the encoding of the output string - it refers to the encoding of the data in the buffer. Unless of course you specify `hex` or `base64`, in which case it does refer to the encoding of the output string. Got it?

### HTTP

Incoming HTTP requests are often encoded using UTF-8. Node will give you data as a Buffer via the HTTP request's `.on('data')` event handler, which can be decoded using the content-type from the HTTP headers. In Express, this is handled in the `body-parser` module, which defers to the `iconv-lite` module for the actual encoding and decoding.

But if you expect e.g. a JSON or XML input, you will probably eventually want to turn that Buffer into a string - see the JSON section below.

When writing string data as an HTTP response, Node will wait until the last possible minute to convert that string into a Buffer that can be written to the socket. This leads to odd behaviors like the `net` library needing to know what encoding to use for a string you pass to it.

### JSON

JSON.parse operates on a string and returns a JSON object, which may be a string or contain strings. JSON.parse and JSON.stringify don't do anything with the string encoding - if you pass in a garbage string, you get a garbage string back out.

So you need to depend on something else to determine the character encoding, _before_ you pass a string to JSON.parse. Usually this will be your HTTP middleware; you have to trust (or verify) that it handles character sets correctly, before creating UTF-8 strings.

### Files on disk

Node source files are expected to be encoded with UTF-8. That means you can encode UTF-8 source characters in a string, like this:

var x = "¢"

Where the cent character is the UTF-8 encoded byte sequence `"\xc2\xa2"`. When Node starts and you try to reference `x` in your program, it will be re-encoded as a UTF-16 string. If you type the literal characters:

var x = "\xc2\xa2";

This will be turned into the UTF-16 string `"\xc2\x00\xa2\x00"`. So be careful to mind your inputs and outputs.

## Conclusion

Encoding in Node is extremely confusing, and difficult to get right. It helps, though, when you realize that Javascript string types will always be encoded as UTF-16, and most of the other places strings in RAM interact with sockets, files, or byte arrays, the string gets re-encoded as UTF-8.

This is all massively inefficient, of course. Most strings are representable as UTF-8, and using two bytes to represent their characters means you are using more memory than you need to, as well as paying an `O(n)` tax to re-encode the string any time you encounter a HTTP or filesystem boundary.

There's nothing stopping us from packing UTF-8 bytes into a UTF-16 string: to use each of the two bytes to store one UTF-8 character. We would need custom encoders and decoders, but it's possible. And it would avoid the need to re-encode the string at any system boundary.