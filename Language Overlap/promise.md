new promise (resolve, reject )=>{

listen for promise state

a promise is a object with multiple properties

like catch, finally, then

.then wraps what ever you pass in , into a new promise so you can contentiously chain

resolve() // when this happens the then is called

reject() // when this is called catch happens

}

function succ(){

    console.log('yeah')

}

var porm = new Promise((resolve, reject)=>{

    setTimeout(()=>{

        // switch between to test

        // resolve()

        reject()

    },2000)

})

// porm.then(succ)

// porm.catch(succ) // almost like a type error or infinite loop never returns anything since catch is for handling reject response not resolve

// porm.then(succ) // similar issue but handling a reject with a then instead of catch

porm.catch(succ)

aysnc function always return promise  and can be used with await to handle errors can use try catch or .then