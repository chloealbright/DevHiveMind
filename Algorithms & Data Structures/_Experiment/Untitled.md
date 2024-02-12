This problem is asking you to reverse the order of words in a given string `s`. A word is defined as a sequence of non-space characters, and words in `s` are separated by at least one space. The goal is to return a string with the words in reversed order, concatenated by a single space.

Constraints include the length of the input string `s` (1 <= s.length <= 10^4), the character types (English letters, digits, and spaces), and the requirement that there is at least one word in `s`.

The follow-up question suggests optimizing the solution for space complexity, specifically if the string data type is mutable, to solve it in-place with O(1) extra space.



Certainly! Here's an imperative approach using loops for reversing the order of words in JavaScript:

```javascript
function reverseWords(s) {
    let wordsArray = [];
    let word = '';

    // Iterate through each character in the string
    for (let i = 0; i < s.length; i++) {
        if (s[i] !== ' ') {
            // If the character is not a space, build the current word
            word += s[i];
        } else if (word.length > 0) {
            // If a space is encountered and a word is being built, add it to the array
            wordsArray.push(word);
            word = ''; // Reset the word for the next iteration
        }
    }

    // Add the last word (if any) to the array
    if (word.length > 0) {
        wordsArray.push(word);
    }

    // Reverse the array of words in-place
    for (let i = 0, j = wordsArray.length - 1; i < j; i++, j--) {
        const temp = wordsArray[i];
        wordsArray[i] = wordsArray[j];
        wordsArray[j] = temp;
    }

    // Join the reversed words with a single space and return the result
    return wordsArray.join(' ');
}

// Example usage:
const example1 = "the sky is blue";
const example2 = "  hello world  ";
const example3 = "a good   example";

console.log(reverseWords(example1)); // Output: "blue is sky the"
console.log(reverseWords(example2)); // Output: "world hello"
console.log(reverseWords(example3)); // Output: "example good a"
```

This code uses loops to iterate through the characters of the input string, build words, and reverse the array of words in-place.