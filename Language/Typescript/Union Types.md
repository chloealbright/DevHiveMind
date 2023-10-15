
Pipe (|) is used to separate each type, so for example number | string | boolean is the type of a value that can be a number, a string, or a boolean 

We can combine two types with a vertical bar character |. This is the syntax for defining a union. Each type in a union is called a type member.






TypeScript lets us type variables with different levels of type specificity. If we want to enforce that a variable is a string, we can type it as a string. This type is very specific since TypeScript will only allow the variable to have a string value. 

On the other end of the specificity spectrum, we could type a variable as any. This type is very unspecific. TypeScript will allow a value of any type to be assigned without complaining and throwing an error. 

These two levels of type specificity work for many parts of our programs. However, sometimes we need to strike a balance between extreme specificity and being totally unspecific with our types. Imagine that we have to write a program that takes in an employee’s ID, then prints the ID to the console. The catch is that an employee’s ID could be a string or a number. Since we need our ID variable to allow more than one type, we could use an any type, like this: 

let ID: any; 

console.log(`The ID is ${ID}.`); 

The problem with the any type is that any value might not work with our program. To solve this problem, TypeScript allows us to be flexible with how specific our types are by combining different types. When we combine types, it is called a union. 

## Defining Unions 

Unions allow us to define multiple allowed type members by separating each type member with a vertical line character |. With a union, we can re-type the program from the previous exercise like this: 

let ID: string | number; 

// number 

ID = 1; 

// or string 

ID = '001'; 

console.log(`The ID is ${ID}.`); 

In this example, string | number is a union that allows ID to be a string or a number. It’s more flexible than a single primitive type, but much more specific than the any type. 

Unions can be written anywhere a type value is defined, including function parameters: 

function getMarginLeft(margin: string | number) { 

  return { 'marginLeft': margin }; 

} 

Using unions to type function parameters is especially convenient because functions often need to handle multiple types of input. 

function printNumsAndStrings(statement: string | number ) { 

  console.log(`ℹ️ LOG:: ${statement}`); 

} 

printNumsAndStrings('hello!'); 

printNumsAndStrings(42); 

## Type narrowing 

function formatValue(value: string | number) { 

  // Write your code here 

  if (typeof value === 'string') { 

    console.log(value.toLowerCase()) 

  } 

  if (typeof value === 'number') { 

    console.log(value.toFixed(2)) 

  } 

} 

formatValue('Hiya'); 

formatValue(42); 

## Inferred Union Return Types 

One of the awesome things about TypeScript is that it’s able to infer types in many cases so that we don’t have to manually write them. A great example is a function’s return type. TypeScript will look at the contents of a function and infer which types the function can return. If there are multiple possible return types, TypeScript will infer the return type as a union. 

For instance, take this example, where we call a function named getBookFromServer(), which might fail: 

function getBook() { 

  try { 

    return getBookFromServer(); 

  } catch (error) { 

    return `Something went wrong: ${error}`; 

  } 

} 

If the call is successful, the function will return a Book type describing a book. If the call fails, the function will return a string. getBook() can return a Book or string type, TypeScript infers the return type as the union Book | string. Since TypeScript can infer the function’s return type, there’s no need for us to manually define it. 

type User = { 

  id: number; 

  username: string; 

}; 

function createUser() { 

  const randomChance = Math.random() >= 0.5; 

  if (randomChance) { 

    return { id: 1, username: 'nikko' }; 

  } else { 

    return 'Could not create a user.'; 

  } 

} 

const userData: string | User = createUser(); 

## Unions and Arrays 

Unions are even more powerful when used in combination with arrays. 

For instance, we can represent time in TypeScript with a number or a string type. If we had a list of dates in both types, we’d need an array that allows for string and number values. Unions are here to help. 

To create a union that supports multiple types for an array’s values, wrap the union in parentheses (string | number), then use array notation []. 

const dateNumber = new Date().getTime(); // returns a number 

const dateString = new Date().toString(); // returns a string 

const timesList: (string | number)[] = [dateNumber, dateString]; 

Above, the timesList variable is typed to allow string and number types as values in its array. If we try to add a value to timesList that is not either type, like with timesList.push(true), TypeScript would display an error that boolean types are not allowed inside timesList. 

One last thing: the parentheses are vitally important to type arrays correctly. If we left out the parentheses and wrote string | number[], that type would allow strings or arrays of only numbers. 

function formatListings(listings: (string | number)[]) { 

  return listings.map((listing) => { 

    if (typeof listing === 'string') { 

      return listing.toUpperCase(); 

    } 

    if (typeof listing === 'number') { 

      return `$${listing.toLocaleString()}`; 

    } 

  }); 

} 

const result = formatListings([ 

  '123 Main St', 

  226800, 

  '580 Broadway Apt 4a', 

  337900, 

]); 

console.log(result); 

## Common Key Value Pairs 

When we put type members in a union, TypeScript will only allow us to use the common methods and properties that all members of the union share. Take this code: 

const batteryStatus: boolean | number = false; 

batteryStatus.toString(); // No TypeScript error 

batteryStatus.toFixed(2); // TypeScript error 

Since batteryStatus can be a boolean or a number, TypeScript will only allow us to call methods that both number and boolean share. They both share .toString(), so we’re good there. But, since only number has a .toFixed() method, TypeScript will complain if we try to call it. 

This rule also applies to type objects that we define. Take this code: 

type Goose = {  

  isPettable: boolean;  

  hasFeathers: boolean; 

  canThwartAPicnic: boolean; 

} 

type Moose = { 

  isPettable: boolean;  

  hasHoofs: boolean; 

} 

const pettingZooAnimal: Goose | Moose = { isPettable: true }; 

console.log(pettingZooAnimal.isPettable); // No TypeScript error 

console.log(pettingZooAnimal.hasHoofs); // TypeScript error 

Like before, since .isPettable is on both Goose and Moose types, TypeScript will allow us to call it. But since .hasHoofs is only a property on Moose, we cannot call that method on pettingZooAnimal. Any properties or methods that are not shared by all of the union’s members won’t be allowed and will produce a TypeScript error. 

type Like = { 

  username: string; 

  displayName: string; 

}; 

type Share = { 

  username: string; 

  displayName: string; 

}; 

function getFriendNameFromEvent(event: Like | Share) { 

  return event.displayName || event.username; 

} 

const newEvent = { 

  username: 'vkrauss', 

  displayName: 'Veronica Krauss', 

}; 

const friendName = getFriendNameFromEvent(newEvent); 

console.log(`You have an update from ${friendName}.`); 

## Unions with Literal Types 

We can use literal types with TypeScript unions. Literal type unions are useful when we want to create distinct states within a program. 

For instance, if we were writing the code that controlled stoplights, we might write a program like this: 

type Color = 'green' | 'yellow' | 'red'; 

function changeLight(color: Color) { 

  // ... 

} 

With the code above, we could ensure that wherever changeLight() is called, that it gets passed only allowed stoplight colors. If we tried to call changeLight('purple'), TypeScript would complain, since that is not a valid stoplight color. 

This technique allows us to write functions that are specific about the states they can handle, which helps us write code that’s less prone to errors. 

type Status = 'idle' | 'downloading' | 'complete'; 

function downloadStatus(status: Status) { 

  if (status === 'idle') { 

    console.log('Download'); 

  } 

  if (status === 'downloading') { 

    console.log('Downloading...'); 

  } 

  if (status === 'complete') { 

    console.log('Your download is complete!'); 

  } 

} 

downloadStatus('complete');