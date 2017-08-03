---
layout: post
title: A Story of Swift
---

I started my career as Software Developer at [Kuliza](https://kuliza.com) in January 2015, within few weeks of my joining, I was asked to join the iOS development team. I was too excited to learn something new, a new technology, a new language. With my background and liking towards Python, I was expecting a new language to be much more fun to learn and I ended up in learning 30+ years old language with boring syntax. It took some time for me to know the disaster of the language by working on a few projects and writing few thousands of lines of code. I wasn’t alone, there were many who felt the same. 

One fine day when I was browsing about the best languages to work with, I was surprised to see the new language that Apple is developing called ‘Swift’. The first thought in my head was why my mentor hadn’t asked me to learn something new in the community, why are we going backward, not learning the language that comes with more merit than its predecessor has to provide. This happened in mid-March 2015, the next day I walked into my mentor’s office and asked him why did he betray me (Sorry for being too dramatic, but I was frustrated). The first thing that I heard from him was a negative comment, the language is too immature to adopt, it is not in its stable state and we can’t afford it right now in our projects. Which was a valid point, but I was intrigued with its continuous evolution, how it is changing over the years to be in a better shape and serve well. From then I have been reading every bit of it through blogs, articles etc. Here is a small story about this new language in the block, Swift.


When I heard about Swift, One of the parallel thoughts that I had was why would a tech giant company like Apple want to replace their own legacy language Objective-C instead of upgrading it. Creating a new language in 2014 is a big decision to make especially Apple to replace their entire App Development structure, while there are many alternative languages in the community. The principle behind creating this new language is to have a compiled, functional programming language faster, safer and lighter that can easily be adopted. The current alternatives are C++, Java, JavaScript Python, Ruby etc. The performance comparison of simple storing operation of these languages with the swift is as follows.

* C++ -o3 : **0.05s**
* C++ -o0 : 0.4s
* Java : 0.2s
* Python with PyPy: 0.5s
* Python : 12s
* Swift -Ofast : **0.05s**
<br>
<sub><sup>*[Source](https://www.quora.com/Why-would-Apple-introduce-new-programming-languages-e-g-Swift-instead-of-embracing-an-existing-one/answer/Glyn-Williams?srid=cSpD)* </sup></sub>

None of the alternative languages fit to the requirement but the closest of all are C++ and Java. We know that Java belongs to someone else, needs a virtual machine and garbage collector. Apple already supported C++, to some extent, we can develop apps in C++ but to use Cocoa (Apple’s UI ToolKit) we may have to switch to ObjC as Cocoa is an ObjC framework. Replacing ObjC, a complicated C-based language with another complicated C-based language doesn’t sound progress. The other alternatives Python and Ruby don’t fit the requirements as they are not compiled languages which is one of the objectives to take advantage of compiler technology. And that is how they ended up in creating new language, Apple is famous for taking bold steps. Fundamentally Swift has elements from all these languages which makes it easier to adopt.

Another interesting aspect of Swift is that it is strongly statically typed language. There are two philosophies here, static type and dynamic type languages. Type system assign rules to types like variables, expressions, functions or modules etc to provide a consistent interface between programs and enable compiler optimizations. The process of checking that the parts have been connected in a consistent way is called Type Checking, that can happen statically at compile time or dynamically at runtime. Statically typed languages are faster than dynamically typed languages. Swift is statically typed language, all classes are created during compile-time. Methods cannot be added on-the-fly and all types are known before the run time. Since everything is known beforehand, a compiler can optimize code without any problem. Objective-C, on the other hand, can’t optimize as effectively, because all dynamic languages work slower than static. Here is a good [article](https://yalantis.com/blog/is-swift-faster-than-objective-c/) which demonstrates the performance by running few experiments to measure the performance of swift using various operations.

Coming back to swift’s origin, it was first released in June 2014, from then it has continuously changed over the years. The main design objective of Swift is to make it easier to learn and adopt with its syntactic sugar syntax along with other goals. Swift is intended to be more resilient to enormous code (safer) than ObjC and more concise. Swift adds the concept of protocol extensibility, an extensibility system that can be applied to types, structs, and classes. Apple promotes this as a real change in programming paradigms they term “protocol-oriented programming”. Swift initially announced in 2014 WWDC conference underwent an upgrade to Swift 1.2. In 2015 WWDC it is upgraded to Swift 2, later that year in December it is open sourced under Apache License from Swift 2.2 version. In 2016 WWDC Swift 3 was announced with a lot of changes to the API naming conventions along with other changes. In March 2017, less than three years after its official debut, Swift made the top 10 in the monthly [TIOBE index](https://www.tiobe.com/tiobe-index/) ranking of popular programming languages.                