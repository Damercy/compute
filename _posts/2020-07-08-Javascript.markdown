---
layout: post
title: Javascript.js
date: 2020-07-08 22:57:00 +0530
permalink: /:title
---
Currently I'm learning `Javascript` and I'm loving it already! But the weird background story is that initially, I didn't _quite like_ JS.

Javascript (JS), much like Python, is a dynamically typed language which just means that unlike languages like C++/Java where we define the datatypes beforehand (pre-compilation phase), we do not need to do so with JS. This is what I mean:

```C++
    // C++ 
    int oopsie;
    int ohWow = 69;
    char really = 'Y';
```

Now the above code snippet is for C++ to define datatypes. It's corresponding JS would probably look like so.
```javascript
    // Javascript
    const oopsie
    let ohWow = 69
    really = 'Y'
```

Now it may not look much different but this small concept of dynamic typing helps with typing out code and not think about the datatype of the variable. But that also means that debugging becomes a nightmare because it's hard to find out which variable exactly caused the issue (which, btw, is why typescript is so popular these days).

Now I didn't like dynamically typed languages because all my life I used C++ and Java to code in and static type checks helped me with debugging and even understand what went behind the scenes of a variable. But now, I think I'm at ease with dynamic typing and hence JS.

### What's confusing in Javascript?
 At first I was confused by the different ways of declaring and defining functions. Here are the different variations:

 ```javascript
    // Variation:1
    function Jude(){
        console.log('Hey!');
    }

    // Variation:2
    let Jude = (){
        console.log('Hey!');
    }

    // Variation:3
    let Jude = () => console.log('Hey!');

 ```

 And then, I was confused with the scopes and applicability of the different variable types.

 ```javascript
    // Scopes
    var iGlobalScope;
    function(){
        var jGlobalScopeAgain;
        let kFunctionalScope;
        const lFunctionalScopeAsWell;
    }
 ```

Finally, callbacks were a bit difficult to grasp.

```javascript
    // Callbacks are essentially functions that call other functions on completion
    setTimeOut(()=>console.log("Display this after 3 seconds."),3000);
```

### What's next?

I need to get my grasp on `Promises`, `Higher Order Functions` and `ES6 classes`. I'll come back with a post on these concepts _soon_.

__Stay tuned!__