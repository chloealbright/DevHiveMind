---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Iterators and Generators bring the concept of iteration directly into the core language and provide a mechanism for customizing the behavior of for...of loops. 

generators acts a wrapper to used built in Iterators 

The function* declaration (function keyword followed by an asterisk) defines a generator function, which returns a Generator object. 

The yield keyword is used to pause and resume a generator function 

Iterators(built in Arrays, Strings, Maps, Sets, NodeList) 

OBJECT => Iterator => Generator 

In JavaScript an iterator is an object which defines a sequence and potentially a return value upon its termination. 

Specifically, an iterator is any object which implements the Iterator protocol by having a next() method that returns an object with two properties: 

value 

The next value in the iteration sequence. 

done 

This is true if the last value in the sequence has already been consumed. If value is present alongside done, it is the iterator's return value. 

Once created, an iterator object can be iterated explicitly by repeatedly calling next(). Iterating over an iterator is said to consume the iterator, because it is generally only possible to do once. After a terminating value has been yielded additional calls to next() should continue to return {done: true}. 

The most common iterator in JavaScript is the Array iterator, which returns each value in the associated array in sequence. 

While it is easy to imagine that all iterators could be expressed as arrays, this is not true. Arrays must be allocated in their entirety, but iterators are consumed only as necessary. Because of this, iterators can express sequences of unlimited size, such as the range of integers between 0 and Infinity. 

```javascript
function* genny(){ 

   yield ''a; 

// a function always return undefined by default 

} 

//let iter = genny(); 

//log(iter) logs object [Generator] {} 

//log(iter.next()); logs {val: 'a', done: false } 

//log(iter.next()); logs {val: undefined, done: true } 

let log = console.log; 

let characters = ['Finn','Poe', 'Rey', 'Kylo', 'Luke', 'Leia'] 

function* genny(){ 

    let i = 0; 

   yield characters[i]; 

    i++; 

    yield characters[i]; 

    i++; 

    yield characters[i]; 

    i++; 

    yield characters[i]; 

    i++; 

    yield characters[i]; 

    i++; 

    yield characters[i]; 

    i++; 

    yield characters[i]; 

    i++; 

    yield characters[i]; 

} 

//let iter = genny(); 

//log(iter) 

//log(iter.next()); 

//log(iter.next()); 

//log(iter.next()); 

//log(iter.next()); 

//log(iter.next()); 

//log(iter.next()); 

//log(iter.next()); 

//log(iter.next()); 

//log(iter.next()); 

let starwars8 = { 

    title: 'The Last Jedi', 

    director: 'Rian Johnson', 

    year: 2017, 

    boxOffice: '1.3B' 

} 

let count = -1; 

let SW8 = { 

    [Symbol.iterator]: function(obj){ 

        return { 

            next: ()=>{ 

                count++; 

                switch(count) { 

                    case 0: 

                        return { 

                            value: obj.title,  

                            done: false} 

                    case 1: 

                        return { 

                            value: obj.year, 

                            done: false 

                        } 

                    case 2: 

                        return { 

                            value: obj.director, 

                            done: false 

                        } 

                    case 3 : 

                        return { value: undefined, done: true} 

                    default: 

                        return { value: undefined, done: true} 

                } 

            } 

        } 

    } 

} 

let data = SW8[Symbol.iterator](starwars8); 

log( data.next() ); 

log( data.next() ); 

log( data.next() ); 

log( data.next() ); 

log( data.next() ); 

// 

//for(let p of starwars8){ 

//    for of loops are using the .next( ) method behind the scenes 

//} 
```

/** 

This second version has two objects - `Obj1` and `Obj2` 

The generator `myGenerator`, is put in the prototype chain for both objects 

This way we can call the [Symbol.iterator] method on each object to give them each their own iterator. 

The new version of the Iterator also checks for the existence of the property, to make this more generic. It will 

display a message about missing properties. 

**/ 

```
let log = console.log; 

let Obj1 = { 

  title: 'The Last Jedi', 

  director: 'Rian Johnson', 

  year: 2017, 

}; 

let Obj2 = { 

  title: 'The Hobbit', 

  director: 'Peter Jackson', 

  boxOffice: '1.017B', 

}; 

let myGenerator = { 

  [Symbol.iterator]: function () { 

    let count = -1; //reset the count 

    return { 

      next: () => { 

        count++; 

        switch (count) { 

          case 0: 

            return { 

              value: this.title ? this.title : 'No title property', 

              done: false, 

            }; 

          case 1: 

            return { 

              value: this.year ? this.year : 'No year property', 

              done: false, 

            }; 

          case 2: 

            return { 

              value: this.director ? this.director : 'No director property', 

              done: false, 

            }; 

          default: 

            return { value: undefined, done: true }; 

        } 

      }, 

    }; 

  }, 

}; 

Object.setPrototypeOf(Obj1, myGenerator); 

Object.setPrototypeOf(Obj2, myGenerator); 

let data1 = Obj1[Symbol.iterator](); //create the iterator for Obj1 

//this sets count to -1 

for (let prop of Obj1) { 

  log(prop); 

} 

log('\n\n'); 

let data2 = Obj2[Symbol.iterator](); //create the iterator for Obj2 

//this sets count to -1 again 

for (let prop of Obj2) { 

  log(prop); 

}
```