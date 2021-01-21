---
layout: post
title: Why Kotlin?
date: 2021-01-21 22:00:00 +0530
permalink: /:title
---

No, this isn't one of those `Top 10 reasons why you should learn Kotlin in 2021`. They're terrible and the only benefit you get from reading such articles is understand _some_ of the features of a particular language/technology. But you want to learn a bit more than that, don't you?

Read on.

### Why Kotlin?
Google introduced Kotlin as the official language for android development after the dispute between Oracle and Google regarding Java as a choice of language  rised considerably. Latest details regarding this can be read [here.](https://www.theverge.com/2020/10/6/21504715/google-v-oracle-supreme-court-hearings-android-java)

Personally, I wasn't much excited in using Kotlin for development as I liked Java's OOP principles in every aspect.  It is easier to think of libraries as classes instead of a blob in other languages (although that's hardly the case, but that's how it is in my head). However, as I began using Kotlin as my primary language for android development, I must say this is nifty language and my perceptions changed!

### The basics
Like javascript, there's const & let equivalent --- `val` and `var` respectively. However unlike const, you needn't initialize the variable at the time of declaration, which is nice. You achieve this feature by using `const` keyword, which also exists in Kotlin and is not to be confused with const keyword's functionality of Javascript.

Like java, there's static types as Int,Boolean,String,Double,Float,Short,Char. Infact they're the exact same Java classes because Kotlin compiles down to same java's bytecode as both languages, unsurprisingly, use the JVM.

Here's a basic Kotlin code:
```kotlin
    class KotlinSample{
        private val aMemberVariable: String
        private var anotherMemberVariable: Int

        private fun aFunction(aParameter:Double){
            return aParameter+2.0
        }
    }

    val classInstance = KotlinSample()
```

Notice there's no use of new keyword to create an instance of a class in Kotlin. I cherish that because I hated writing new everytime. Seemed repetitive.

### Up the ante
Kotlin introduces extra features like extension functions, data classes & nullsafety. These are the major ones I've come across in my use case. There are much, much more features but alas I know so much & you read so little.

#### Nullsafety
`?.` is known as safe-call operator. It performs a null safety check and based on this check, proceeds further.

```kotlin
    val isNull = null
    val isNotNull = "Yay!"

    val result = isNull?.
                "This isn't value of result"?:
                "This is actually value of result"
```
Thus the format `x?.y?:z` is read as ___if x is not null, do y else do z___. Saves you a bunch of if-else, eh?

#### Extensions functions
You've got a String class. You want to perform some operation specifically on strings but you don't want to create an entirely different function in a separate package/class. Welcome extension functions. They help you _extend_ the functionality of existing classes, like String in our case, by giving you the ability to write extra logic, like functions.

```kotlin
    class Weirdo( val name:String)

    fun main(){

    fun Weirdo.myCustomOperation(someName:String):String{
            return someName.toUpperCase()
    }

    val aWeirdo = Weirdo("Dayamoy Adhikari")
    val nameUpperCased = aWeirdo.myCustomOperation(aWeirdo.name)
    println(nameUpperCased)
}
```

Pretty sweet!

#### Data classes
Java was notoriously famous for having repetitive patterns of creating classes purely for holding data, also known as POJO's. Kotlin solves this elegantly by using a special kind of class called data class. It's simple. Define a class with the keyword `data`, and all it'll do is hold data for you in a class, unless ofcourse you want it to perform some more operations which,btw, it can do as well.

```kotlin
    data class myNetworkResponseObject(
        private val fieldOne:Int,
        private val fieldTwo:String
    )
```

That's it! It generates all the redundant toString(),hashCode(),getters & setters methods in Java data classes for you.

