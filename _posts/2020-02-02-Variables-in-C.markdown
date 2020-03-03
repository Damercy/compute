---
layout: post
title: Not all variables are the same (in C)
date: 2020-02-02 22:55:00 +0530
permalink: /:title
---
![img](/compute/images/storage-classes.jpg "Variables in a nutshell")  

Please don't fret on seeing just another article about those "basic storage classes in C"! It's interesting!  

There exists primarily four storage classes in the C programming language:
1. Automatic (auto)
2. Register
3. Static
4. Extern  

( In case you want to remember the names, simply learn **`A.R.S.E.`**)  

#### But why call them Storage 'Classes' ?
---  
If you ask me that why are they called classes, I'd say it's probably because `they contain metadata about a variable`, just like a generic class would i.e.If a class contains data about something, a storage class contains data about storage (variables). Storage classes contain information about a variable like access permissions via scopes, lifetime of a variable, the memory location of a variable & default value.  

#### Ah, Sweet naming convention! What's more?
---  

Each of the 4 storage classes have 4 attributes viz. memory,initial value,scope,lifetime. (check the above picture)  
**Memory**: Where a variable that has been declared should be allocated memory(space) to. It's usually the primary memory (RAM), but can be specified to the Register memory of a CPU as well.  
**Initial value**: This is the default value that a declared variable should "hold" (contain).  
**Scope**:  In simple terms, it defines the accessibility of the variable. If a variable is out of a block's scope, it's inaccessble.  
**Lifetime**: It defines the time for a which a variable remains valid. A lifetime of a variable ends when the memory for the variable has been de-allocated (freed).  

In case you feel overwhelmed, here's a *quick* joke for you:  
```
What's the difference between a variable and me?

At least a variable has scope.
```

Just try to have some clarity between scope and lifetime, as most people tend to ignore the small difference between them. I know I've been guilty of it.  

#### Okay! But what good are these to me?
---  
So imagine you have a large codebase with 1000+ lines of code. In here, you've defined some variables that act as a counter which increments/decrements it's value based on some condition. Since you've simply defined it as a normal variable, it's an auto variable now, right? So which memory are auto variables stored in? Yep, the RAM.  

So each time these counter variables are referred to in your huge codebase, the CPU has to literally reference to the memory location of the variable every time. And that's just stupid!  

To put things in perspective, imagine you've got two friends -------- Peter and Bruce.  
>
**Peter**: Hey,{your name}, do you have the address of Bruce?  
>
**You**: Nah, but wait let me ask Bruce and I'll let you know.  
>
.....*After knowing address from Bruce*.....  
>
**You**: Here's the address, Peter.  
>
**Peter**: Thanks!  
>
.....*Later in the day*.....  
>
**Peter**: Hey, I'm sorry I lost the address, what was Bruce's address again?  
>
**You**: Um, so... Well.. Let me ask Bruce and I'll let you know.  
>
.....*After knowing address from Bruce*.....  
>
**You**: Here you go.  
>
**Peter**: Thanks again!  
>
.....*Much later in the day*.....  
>
**Peter**: Ah dude, I lost it. Bruce's address, one last time?  
>
**You**: Let me ask Bruce and I'll let you know.  

You get the point? You are the stupid. That's the point. Yep.  (What's that? Peter is stupid too? **NO.**)

But you can be less stupid if you write down Bruce's address and keep it closer to you, so that you don't have to travel to Bruce's home to get his address (No, phone's haven't been invented yet).  

The counter variable can be stored in the register memory of the CPU so that it doesn't have to reference it's memory location every time it is been referred to.  

And how do you make a variable store in the register memory? Yes! Declare it as a `register` type. It helps to execute your code a little bit faster. But be cautioned, due to the limited memory of CPU registers when compared to primary memory, you cannot declare too many variables as register type with the hope of making your entire program run blazin' smooth!  

#### Alright! I see the point now!
---  
That's good to hear! The rest of the variables have their own use-case as well which you can further read about on your own.  

But to conclude about them in short, the `static` variable is useful when you want to pass a variable between different functions (modules) of the same code while the `extern` variable finds it's use case when you've variables declared in other files of your project which you want to use in your current file.  

It's so easy to forget about the different types of these storage classes that are available to us, and that's primarily because we hardly care to apply them in real life code. I really hope I can apply them in the things I build in the future.  

#### For I must remember,***" Not all variables are the same. "***