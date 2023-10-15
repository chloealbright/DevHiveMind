Tackling performance often crops up in JavaScript applications. 

Throttling and debouncing give us control over the rate at which a function is called. They are need to know techniques for any web developer. They are especially useful when we are dealing with event handler assignments. There are scenarios where we may invoke functions when it isn’t necessary. Consider a callback that we want to execute on window resize. Does it make sense to fire the callback as we resize? Most likely not. We want to wait til the user has finished interaction and then fire the callback. 

What’s the difference between throttling and debouncing? 

Throttling — If you think of a car throttle. The amount you push your foot down limits the amount of gas going into the engine. In this context, we want to limit the amount a function is invoked. I find a better analogy to be either the lottery, only one ball is drawn every five seconds. Or a better analogy being ordering drinks at a bar. You go to a bar and the barman has a policy of only allowing you to order a drink every 45 minutes (Or things get crazy). You order a drink in the first minute and they hand one over. You then try and order one every minute after. The barman denies you until the 45th minute when the then tired barman hands over the next drink. You won’t get another drink for another 45 minutes. With throttling, you may want one last invocation to happen after the throttle is over. This will be one of the denied invocations. Imagine you order a drink in the 15th minute and get denied. In the 45th minute, you don’t order but the barman sends a waiter over with the drink from that 15th minute order. They feel sorry for you 😁 

Debouncing—Debouncing works a little different. It can be a little harder to explain. With debouncing, it’s like “Hey, I’m not going to execute that function until I know there are no more changes inbound”. We don’t execute our function until everyone else is happy and we’re clear to proceed. Imagine ordering food at a restaurant. You start listing off items to the waiter/waitress and at the end they ask “Is that everything?” If it is, they leave you to it and go get your food and drinks. If it isn’t, you add to the order and then they ask you again until they are clear to proceed. 

Example use cases: 

Throttling a button click so we can’t spam click 

Throttling an API call 

Throttling a mousemove/touchmove event handler 

Debouncing a resize event handler 

Debouncing a scroll event handler 

Debouncing a save function in an autosave feature 

Let’s consider an example for each. Throttling is likely used less than debouncing. More often than not, when you consider throttle use, you may be better with debounce. If you have a good use case for throttling, please let me know! 

For throttling, let’s consider that first use case, stopping click spamming. We have a button in our app that when clicked, makes an API call of some kind. Let’s say to enter a competition. With throttling we can restrict the amount the API would get hit. The user may be clicking 20 times a second but we only fire the handler once per second. 

For debouncing, let’s consider the auto save feature. Auto save tries to save the state of the application every time the user makes an update or interacts. We can debounce the save until a user hasn’t made any updates or interacted for a set period of time. That way we don’t spam the save function and make unnecessary saves. This will help performance. 

Implementing throttle and debounce 

There are various implementations of throttle and debounce. The majority will achieve the same goal. Their implementations revolve around the use of setTimeout. 

// more simpler 

const debounce = (func, delay) => { 

  let inDebounce 

  return function() { 

    const context = this 

    const args = arguments 

    clearTimeout(inDebounce) 

    inDebounce = setTimeout(() => func.apply(context, args), delay) 

  } 

} 

We are passing a function(func) and a delay(delay) into the debounce function. inDebounce is a variable that we use to track the delay period. 

If we are invoking for the first time, our function will execute at the end of our delay. If we invoke and then invoke again before the end of our delay, the delay restarts. It’s much easier to understand by reading the code and playing with the demo 😉. 

Here’s how that debounce looks in action. 

debounceBtn.addEventListener('click', debounce(function() { 

  console.info('Hey! It is', new Date().toUTCString()); 

}, 3000)); 

Throttle 

Throttle can be a little taxing as its desired behaviour has different interpretations. Let’s start by limiting the rate at which we execute a function. 

const throttle = (func, limit) => { 

  let inThrottle 

  return function() { 

    const args = arguments 

    const context = this 

    if (!inThrottle) { 

      func.apply(context, args) 

      inThrottle = true 

      setTimeout(() => inThrottle = false, limit) 

    } 

  } 

} 

The first call to our function will execute and sets the limit period inThrottle. We can call our function during this period but it will not fire until the throttle period has passed. Once it has passed, the next invocation will fire and the process repeats. 

throttleBtn.addEventListener('click', throttle(function() { 

  return console.log('Hey! It is', new Date().toUTCString()); 

}, 1000)); 

But what about our last call? If it’s in the limit period it’s ignored and what if we don’t want that? For example, if we bound to mouse movement for a resize and missed the last call we’d never get the desired result. We need to catch this and execute it after the limit period (Thanks to  

world war for questioning the previous implementation which didn’t always work 100% as expected). 

const throttle = (func, limit) => { 

  let lastFunc 

  let lastRan 

  return function() { 

    const context = this 

    const args = arguments 

    if (!lastRan) { 

      func.apply(context, args) 

      lastRan = Date.now() 

    } else { 

      clearTimeout(lastFunc) 

      lastFunc = setTimeout(function() { 

        if ((Date.now() - lastRan) >= limit) { 

          func.apply(context, args) 

          lastRan = Date.now() 

        } 

      }, limit - (Date.now() - lastRan)) 

    } 

  } 

} 

This implementation ensures that we catch and execute that last invocation. We also invoke it at the correct time. We do this by creating a variable lastRan which is a timestamp of the last invocation. We can then use this to determine if the last invocation took place within the throttle limit. We can also use lastRan to determine whether the throttled function has ran at all. This makes the previous variable inThrottle redundant. 

One way to think about this implementation of throttle is like a chaining debounce. Each time the debounce waiting period lessens. 

throttle has some interesting possibilities. For example, you could store all the ignored executions and run them all at the end in order. 

https://webdesign.tutsplus.com/tutorials/javascript-debounce-and-throttle--cms-36783