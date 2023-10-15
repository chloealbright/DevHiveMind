Typescript any

When a variable is declared without being assigned an initial value, TypeScript considers it to be of type any. A variable of this type can be reassigned without generating any error from TypeScript.

let first;

first = 'Anders';

first = 1337;