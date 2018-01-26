---
layout: post
current: post
cover:  assets/images/covers/jussara-romao-335086.jpg
navigation: True
title: The Chair is Black (or What You Could Do With a Second Brain)
class: post-template
subclass: 'post tag-getting-started'
author: mathieu
categories: welcome mathieu
---

I recall as a teenager being totally absorbed by the reading of a great 1948 sci-fi novel by A. E. van Vogt named [The World of Null-A](https://en.wikipedia.org/wiki/The_World_of_Null-A), in which the amnesic main character, Gilbert Gosseyn, discovers he has grown a second brain allowing him to memorize scenes with extreme detail and precision. He can later teleport himself back to those places by simply evoking its photographic memories. He discovers that perceiving things in their finest details is the secret art of *non-Aristotelian logic*, mastered solely by the peaceful and discreet detective people of Venus.

As I remember, Van Vogt advanced that, according to *non-Aristotelian logic*, objects should not be reduced to their simplest attributes, but rather considered as rich and vastly complex realities. For example, he says that stating *the chair is black* is reductionist, because the chair is certainly many more things than just *black*. It might, all at once, be *shiny*, *tall*, *wooden*, *art-deco*, *fragile*, *worn*, *hand-made*, *slightly chipped at the bottom of one leg*… well, you get the point.

And that's an interesting point to make, philosophically speaking. Applied to software design, we could take it as advice for considering problems holistically, with a fine understanding of their very details. However, I would argue that, conversely, once you have that global picture in mind, the role of a software designer or architect is precisely to break up and reduce complex problems into smaller conceptual chunks.

Not being gifted with Gilbert Gosseyn's second brain, we need to dissect, simplify and distil a potentially infinite reality into much less exhaustive (though workable) *abstractions*.

# But what exactly *is* abstraction?

Formally, *abstraction* comes from the Latin *abs* (away from) and *trahere* (to draw) and is the reduction of something to a set of essential characteristics. But let me try and put it in a very code-centric way:

> An abstraction is a simplified representation of some entity, purposefully chosen for a specific context, allowing another entity to relate to it, yet without coupling them together.

Wow, that's a lot to take in at once, so let's take it apart...

## It's a simplified, context-specific representation

It does not (nor should it try to) capture the entity in its whole, with all its capabilities and glory. It only represents a very limited subset of its characteristics. However, *which* characteristics should be selected depends on the *context* (in other words, the *intention* or *purpose*).  Completely different subsets might be drawn from the same entity in different contexts.

>  Let's take *Liam*, some lovely fictitious human being, and see the various abstractions he exposes, in different contexts (in the form of C# interfaces!) While he boasts an `ICertifiedPublicAccountant` interface, which is the only one his boss cares and wants to know about, his colleagues also appreciate him via his `IFerociousTeamFortressPlayer` interfaces. His friends rely on his `IAmAlwaysThereWhenYouNeedMe` interface and his kids crave his `IRitualSundayMorningPancakeMaker` and `ILovelyBedtimeStoryReader`, among so many others. And, of course, he has a secret `IBestLoverUnderTheSheets` interface, but that one is solely reserved to his wife's benefits. And, ultimately, as all fellow human beings, he has the dreadly `IDisposable` interface, for his final hour.

## It allows things to connect or relate

An abstraction is intended to *connect* - at the same time as *isolate* - two different parties, allowing them to interact and collaborate via a straightforward channel, while preserving as much independence between them as possible, allowing either one to be replaced without much affecting the other. Those two parties and the abstraction between them can take on different names, such as client-(API)-server, consumer-(contract)-service, subscriber-(subscription)-publisher, employer-(job title)-employee, listener-(speech)-speaker, usage-(interface)-implementation...

## Yet keeps them apart

without letting their respective details make them dependent upon each other.

## It allows to replace either one

Dependency Injection

Strategies

## It allows to intercept and/or delegate

Decorators

Composites



## Man creates abstractions (because they are useful)

And we sometimes refer to them as interfaces, protocoles, standards, contracts, languages, idioms, job titles, buttons, control panels, etc.

Any kind of interface, physical or virtual, is an abstraction, starting with your remote's *play* button, all the way to your oven's control panel. Even your fridge's light switch is an abstraction of the door's actual *open* or *close* state, allowing the light to turn on or off along with the door opening or closing. And it's really just an *abstraction* of that concept - *not the real thing* - because if you barely open the door, the light won't turn on yet, even if the door is actually *open*. You may also replace the door with any other door, and the light switching mechanism will work just as well. And, as a kid, you surely must have enjoyed fooling the light into thinking the door was closed by pressing your finger against the switch (yeah right, don't tell me you never did!)

## Nature creates abstractions (because they are useful)

Anything that interfaces between two parties and conveys meaning is a form of abstraction. There are countless examples in nature and our body.

Our nerves...

Cells, hormones and proteins...

## Abstractions in C# #

Most programming language constructs are forms of abstraction.

In C#, interfaces, methods, delegates and lambdas all expose some operations that can be performed, isolating the *who* wants them to be performed (and *why* and *when*) from *who* is actually going to perform them (and especially *how*).

The most powerful and useful form is *interfaces*, so I will especially focus on them.

## The interface segregation principle (or *small is beautiful*)

Our dear friends at [Wikipedia](https://en.wikipedia.org/wiki/Interface_segregation_principle) have this to say:

> The **interface-segregation principle** (**ISP**) states that no client should be forced to depend on methods it does not use. ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them. […] ISP is intended to keep a system decoupled and thus easier to refactor, change, and redeploy.

More concisely, I would say:

>  Smaller interfaces are easier to implement, consume and understand and, as such, are more usable, reusable, flexible and pluggable.

And I would even dare advance that, generally-speaking:

> The level of abstraction of an interface is *inversely* proportional to its complexity.

That complexity can be roughly measured in function of the number of members it contains, as well as the number and complexity of parameters in its methods.

In other words, the power of an interface resides in its simplicity. Indeed, *Small Is Beautiful*.

Let's start with a real-world example

- Ex: The doorbell is a great and super useful abstraction

  - Everybody knows how to use it and even expect it, no matter which house they go to
  - Everybody knows what it means and what to do when the doorbell rings, even in someone else’s house.
  - One of the reasons it’s so useful is its simplicity

  Abstraction inversely proportional to complexity

  - The level of abstraction of an interface is inversely proportional to its number of methods, and to the number and complexity of parameters in those methods.
  - The most abstract interface would include a single method with no parameters
  - Ex: IDoorbell.Ring()
  - Ex: IDisposable
  - In fact, even more abstract would be an empty interface, whose only presence is sufficient to carry much meaning
  - Not much expressive and rich
  - But highly useful and powerful, precisely *because* of that simplicity

### About SOLID principles

The *ISP* is only one of the five [SOLID principles](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)), which are at the core of understandable, flexible and maintainable software design. If you don't know them, I would strongly recommend you take the time to learn and put them in practice as much as possible in your projects. I will come back to some of those principles in future blog posts.

# Conclusion

I believe that the mastery of navigating levels of abstraction and constantly figuring what is truly relevant in every given situation is probably one of the most important skills a programmer could develop throughout his/her career.

In this blog, I will share my thoughts and findings on all sorts of software development topics, from patterns to best practices, through technologies and frameworks, but most of the time with abstraction as an underlying thread.

My next post, I promise, will shift from this very high, philosophical level, to the much lower and more concrete level of C#. More precisely, what abstraction levels are built into C# and how to take advantage of them.

In the meantime, go on, contemplate the numerous abstractions that surround us and, next time someone asks you where to sit, simply reply *the black chair*.
