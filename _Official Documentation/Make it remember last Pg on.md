---
tags:
  - Official-Documentation
author: jacgit18
Status: done
Started: 
EditDate: 
Relates:
---


https://repost.aws/knowledge-center

https://aws.amazon.com/whitepapers/?whitepapers-main.sort-by=item.additionalFields.sortDate&whitepapers-main.sort-order=desc&awsf.whitepapers-content-type=*all&awsf.whitepapers-tech-category=*all&awsf.whitepapers-industries=*all&awsf.whitepapers-business-category=*all&awsf.whitepapers-global-methodology=*all

https://aws.amazon.com/blogs/aws/





https://www.postgresql.org/docs/current/index.html

https://www.pgadmin.org/docs/pgadmin4/latest/index.html


https://sqlbolt.com/lesson/select_queries_introduction

https://dev.to/iainfreestone/20-resources-for-generating-fake-and-mock-data-55g1

https://www.softwaretestinghelp.com/login-page-test-cases/

https://www.section.io/engineering-education/how-to-generate-fake-data-in-node-using-faker.js/


https://kubernetes.io/docs/home/

https://docs.docker.com/?_gl=1*1oyqks4*_ga*MTY1NjI3MDQxMS4xNjkxODY1OTQ1*_ga_XJWPQMJYHQ*MTY5ODUzODQ5OS4yLjEuMTY5ODUzODUwMC41OS4wLjA.



https://docs.obsidian.md/Home


https://git-scm.com/doc

https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests

https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud

https://docs.github.com/en/get-started/quickstart/github-flow

https://docs.github.com/en/actions

https://github.com/features/copilot

https://docs.github.com/en/copilot

https://www.freecodecamp.org/news/how-to-use-github-copilot-with-visual-studio-code/

https://www.kali.org/docs/

https://www.kali.org/tools/all-tools/



https://learning.postman.com/docs/introduction/overview/

https://web.postman.co/bootcamp

https://code.visualstudio.com/


https://www.typescriptlang.org/docs/handbook/2/basic-types.html





https://code.visualstudio.com/docs/typescript/typescript-debugging


https://www.digitalocean.com/community/tutorials/how-to-debug-react-components-using-react-developer-tools

https://jkettmann.com/react-debugging-session-hundreds-of-function-calls






https://www.digitalocean.com/community/tutorials/how-to-use-generics-in-typescript

https://js.checkio.org


https://github.com/gopinav/Redux-Toolkit-Tutorials/tree/master/react-rtk-demo/src


// Array
// last
// makeArr: 2 generics, return, overwrite inference, default value
// addFullName: extends
// interfaces
// props
// useState
// jsx generic



const last = <T>(arr: T[]): T => {
  return arr[arr.length - 1];
};


`const last = <T>(arr: T[]): T => { ... }`

- `<T>`: This defines a generic type parameter `T` for the function. It means that the function can work with arrays of any type.
- `arr: T[]`: The `arr` parameter is an array of type `T`, which means it can be an array of any data type.
- `T`: The function returns a value of type `T`, which is the same type as the elements in the array.

- If you call `last([1, 2, 3])`, `T` is inferred as `number` because the array contains numbers. So, the function returns the last element as a number.
    
- If you call `last<string>(["a", "b", "c"])`, you explicitly specify `T` as `string`. In this case, the function returns the last element as a string.

const l = last([1, 2, 3]);

const l2 = last<string>(["a", "b", "c"]);

const makeArr = <X, Y>(x: X, y: Y): [X, Y] => {
  return [x, y];
};

const v = makeArr(5, 6);
const v2 = makeArr("a", "b");
const v3 = makeArr<string | null, number>("a", 5);

const makeFullName = <T extends { firstName: string; lastName: string }>(
  obj: T
) => {
  return {
    ...obj,
    fullName: obj.firstName + " " + obj.lastName
  };
};


1. `<T>`: This is a generic type parameter, which allows you to make a function or type more flexible by accepting different types. In this case, it's named `T`, but you can use any name you prefer.
    
2. `extends`: The `extends` keyword is used to set a constraint on the generic type `T`. It restricts `T` to only be a type that extends the specified structure.
    
3. `{ firstName: string; lastName: string }`: This is an object type literal. It defines an object with two properties: `firstName` and `lastName`, both of which must be of type `string`.
    

So, when you see `<T extends { firstName: string; lastName: string }>` in a function or type definition, it means that `T` can be any object type as long as it has at least `firstName` and `lastName` properties, both of which are of type `string`. This constraint ensures that you can safely access `firstName` and `lastName` properties on objects of type `T` within the context of that function or type.


const v4 = makeFullName({ firstName: "bob", lastName: "junior", age: 15 });
// const v5 = makeFullName({ another: "bob", lastName: "junior", age: 15 });

interface Tab<T> {
  id: string;
  position: number;
  data: T;
}

1. `interface Tab<T>`:
    
    - `Tab` is an interface that is generic, meaning it can work with various data types.
    - The `<T>` in `Tab<T>` represents a placeholder for a specific data type that will be used when implementing this interface.
    - Inside the interface definition, there are three properties:
        - `id` is of type `string`.
        - `position` is of type `number`.
        - `data` is of type `T`, which means it can be of any type, depending on how the interface is used.
2. `type NumberTab`:
    
    - `NumberTab` is a type alias that uses the `Tab` interface with the type `number`.
    - This means that it specifies a data type for the generic `T` in the `Tab` interface as `number`.
    - `NumberTab` is essentially a shorthand for objects that conform to the `Tab<number>` structure, where the `data` property should be of type `number`.
3. `type StringTab`:
    
    - Similarly, `StringTab` is another type alias that uses the `Tab` interface with the type `string`.
    - It specifies that objects conforming to the `StringTab` structure should have the `data` property of type `string`.


type NumberTab = Tab<number>;
type StringTab = Tab<string>;


const numberTab: NumberTab = {
  id: "tab1",
  position: 1,
  data: 42
};

const stringTab: StringTab = {
  id: "tab2",
  position: 2,
  data: "Hello, World"
};
