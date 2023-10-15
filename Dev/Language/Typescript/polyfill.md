A polyfill is a piece of code (usually JavaScript on the Web) used to provide modern functionality on older browsers that do not natively support it. 

For example, a polyfill could be used to mimic the functionality of a text-shadow in IE7 using proprietary IE filters, or mimic rem units or media queries by using JavaScript to dynamically adjust the styling as appropriate, or whatever else you require. 

The reason why polyfills are not used exclusively is for better functionality and better performance. Native implementations of APIs can do more and are faster than polyfills. For example, the Object.create polyfill only contains the functionalities that are possible in a non-native implementation of Object.create. 

Other times, polyfills are used to address issues where browsers implement the same features in different ways. The polyfill uses non-standard features in a certain browser to give JavaScript a standards-compliant way to access the feature. Although this reason for polyfilling is very rare today, it was especially prevalent back in the days of IE6 and Netscape where each browser implemented JavaScript very differently. The 1st version of JQuery was an early example of a polyfill. It was essentially a compilation of browser-specific workarounds to provide JavaScript developers with a single common API that worked in all browsers. At the time, JavaScript developers were having major problems trying to get their website to work across all devices because there was such a discrepancy between browsers that the website might have to be programmed radically differently and have a much different user interface based upon the user's browser. Thus, the JavaScript developer had access to only a very tiny handful of JavaScript APIs that worked more-or-less consistently across all browsers. Using a polyfill to handle browser-specific implementations is less common today because modern browsers mostly implement a broad set of APIs according to standard semantics. 

Example you need to know the inner workings of the thing you want to poly-fill 

const arr = [1,2,3,4,5] 

// Simulate browser incompatibility 

Array.prototype.forEach = null 

if(!Array.prototype.forEach) 

{ 

   Array.prototype.forEach = function(callbackFunction){ 

   for(let val of this) 

        callbackFunction(val) 

   } 

} 

arr.forEach((val) => { 

    console