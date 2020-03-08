---
layout: post
title: Treasure maps
date: 2020-03-08 19:32:00 +0530
permalink: /:title
---

I've been using this really cool data structure in programming langugaes since about 3 months now. It's a `map`.

Or as I like to call it, treasure maps!

Maps are an efficient data structure that use hash tables in the background to provide a constant-lookup time [O(1)]. And as the interview guides and the greats of the internet say, maps are in heavy use in coding. But if you ask me, I would say the same too and that's because I've experienced the power of maps. Firsthand.

Before I show you an application of maps, let me write about the _little_ hashing that I know.

Hashing is a technique in which a data is mapped in a data structure, preferably a hash table. Hash tables employ hashing functions to convert a given value into a hashed value for storing in the table.

> But hey, why use hashing in the first place? Why not store the data directly in the table itself?

Glad you asked, stranger! You see, if you were to store `n elements`, the amount of space required would be **O(n)**, but more importantly, the time taken to search these `n elements` would be O(n) as well which, by definiton, isn't good enough when compared to a constant-time of **O(1)**. So hoomans, far intelligent than you & me, have devised ways to _convert_ O(n) look-up time to O(1). **Seems magical, right?**

But out goes the magic when in comes the mathematics. Now, I am no mathematician nor good at it, but goddamn I know about **_the modulo operator_**. The modulo operator ('**%**'), just like any operator (say, '**+**'), performs on binary operands (say, **a** and **b**) to return the remainder. For example, **7%2=1** (Since, 7 divided by 2 yields 1).

The modulo operator serves as the base of many `basic`/ `primitive`/`simple hashing functions`. You see, the hashing function is one of the key factors behind the efficient look-up time. And this function, as you may've guessed by the name function, is derived (generated) mathematically. Each data has it's own set(s) of efficient hash function(s).

Wrapping up, hash tables use hash functions to map a value into it's corresponding index (place). The following picture might help for you visual learners out there!

![img](/compute/images/hashing.png "Hash-baby,daddy's-here")

You run a value(key) through the hash function which spits out an index that's in the range of the hash table and you put this value (key) in the spitted out index.

Now all of this might seem unnatural and non-intuitive, for I had felt the same when I learnt about hashing the first time, but if you read more in-depth about hash tables, you'll be convinced. There's several concepts to discuss like how to decide a hash function, the different methods of hashing, ways to resolve collision in hash tables, salting in hashtables etc. But alas, you've got only so much patience and I, so little knowledge.

Now, here's an instance of how _treasure_ maps are applicable in real-life/ programming. Here's a common coding problem.

#### **Q: Given a string of characters, find out the frequency of each character.**

#### **Example:** Input string: "HashBabyHash"

#### **Output:** 'H': 2, 'a': 3, 's': 2, 'h': 2, 'B': 1, 'b': 1, 'y': 1

A brute force approach would involve using two-loops, iterating over each element, comparing with the next and incrementing the counter when we hit a duplicate.

```python
def brutus_maximus(string):
    solution_list = []
    solution_list_count = []
    counter = 1
    for index1 in range(len(string)):
        for index2 in range(index1+1,len(string)):
            if string[index1]==string[index2] and string[index1] not in solution_list:
                counter+=1
        if string[index1] not in solution_list:
            solution_list.append(string[index1])
            solution_list_count.append(str(counter))
        counter = 1
    for key,value in zip(solution_list,solution_list_count):
        print(key+":"+str(value))


string = "HashBabyHash"
x = brutus_maximus(string)
```

Isn't that a **_long_** code? I know.

So the great minds have devised the **hashing way-of-life** to reduce the codesize into a meagre-size as shown in the following code. This uses hash tables, also known as a dictionary in python.

```python
def treasure_map(s):
    map = dict()
    for char in s:
        if char in map:
            map[char]= map[char]+1
        else:
            map[char]=1
    return map


string = "HashBabyHash"
x = treasure_map(string)
print(x)
```

See how the code has reduced, and more importantly, the `readability` increases? I think an average person would much rather read through the second _"reduced"_ code than the first _"overwhelming"_ one.

And that, all because of hashtables.

In real-life, hash tables are largely used by **Facebook** to store user information as key value pairs, aka dictionary aka hash table to allow for fast look-up and retrieval. **Encryption algorithms** use `salting` concept in hashing to enforce better security. There's so many applications that I am limited by my knowledge and blog post length.

Hash tables are widely used to map real life data to an abstract concept.

It's the map to the treasure we find.

Thanks for reading!
