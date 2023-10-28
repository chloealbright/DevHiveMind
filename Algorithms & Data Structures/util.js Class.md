---
tags: 
author: 
Status: 
Started: 
EditDate: 
Relates:
---
// These functions are designed to be exported, but you could create a class instead. See tutorial video.  

// #1 proper case 

export const properCase = (string) => { 

    return `${string[0].toUpperCase()}${string.slice(1).toLowerCase()}`; 

}; 

// #2 console log 

export const log = (content) => { 

    console.log(content); 

} 

export const info = (arg) => console.info(arg) 

export const warn = (arg) => console.warn(arg) 

export const error = (arg) => console.error(arg) 

export const table = (arg) => console.table(arg) 

// #3 query selector with optional scope  

export const select = (selector, tagElementScope) => { 

    return (tagElementScope || document).querySelector(selector); 

} 

! is the logical negation or "not" operator. !! is ! twice. It's a way of casting a "truthy" or "falsy" value to true or false, respectively. Given a boolean, ! will negate the value, i.e. !true yields false and vice versa. Given something other than a boolean, the value will first be converted to a boolean and then negated. For example, !undefined will first convert undefined to false and then negate it, yielding true. Applying a second ! operator (!!undefined) yields false, so in effect !!undefined converts undefined to false. 

// #4 addEventListener wrapper  

export const listen = (target, event, callback/Middleware, capture = false) => { 

    target.addEventListener(event, callback, !!capture); 

} 

const eventLog  = (e) =>  console.log(e.target); 

listen(body, "click",  eventLog, ) 

// #5 sanitize input / escape characters also regex can be used 

export const sanitizeInput = (inputValue) => { 

    const div = document.createElement('div'); 

    div.textContent = inputValue; 

    return div.innerHTML; 

} 

const dirtyInput = "<script>alert('xss attack')</script>&othervalues" 

const cleanInput = sanitizeInput(dirtyInput) // replaces < > and & 

// #6 create an element with an optional CSS class 

export const createElement = (tag, className) => { 

    const el = document.createElement(tag); 

    if (className) el.classList.add(className); 

    return el; 

} 

// #7 delete all contents 

export const deleteChildElements = (parentElement) => { 

    let child = parentElement.lastElementChild; 

    while (child) { 

        parentElement.removeChild(child); 

        child = parentElement.lastElementChild; 

    } 

} 

// #8 add class with optional query scope 

export const addClass = (selector, className, scope) => { 

    (scope || document).querySelector(selector).classList.add(className); 

} 

// #9 check for iOS 

export const isIOS = () => { 

    return ( 

        (/iPad|iPhone|iPod/.test(navigator.platform) || 

            (navigator.platform === "MacIntel" && navigator.maxTouchPoints > 1)) && !window.MSStream //MSStream is to avoid IE11 

    ); 

} 

// #10 get parameters by name from url 

export const getParameterValue = (paramName, url) => { 

    if (!url) url = window.location.href; 

    const regex = new RegExp(`[?&]${paramName}(=([^&#]*))`); 

    const results = regex.exec(url); 

    if (!results) return null; 

    if (!results[2]) return ""; 

    return decodeURIComponent(results[2].replace(/\+/g, " ")); 

} 

alt utils 

https://gist.github.com/ahmad-511/79f62262e96113225ddddd9f7b4c848f