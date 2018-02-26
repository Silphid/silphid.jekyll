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
typora-root-url: ../assets
---

I recall as a teenager being totally absorbed by the reading of a great 1948 sci-fi novel by A. E. van Vogt named [The World of Null-A](https://en.wikipedia.org/wiki/The_World_of_Null-A), in which the amnesic main character, Gilbert Gosseyn, discovers he has grown a second brain allowing him to memorize scenes with extreme detail and precision. He can later teleport himself back to those places by simply evoking its photographic memories. He discovers that perceiving things in their finest details is the secret art of *non-Aristotelian logic*, mastered solely by the peaceful and discreet detective people of Venus.

As I remember, Van Vogt advanced that, according to *non-Aristotelian logic*, objects should not be reduced to their simplest attributes, but rather considered as rich and vastly complex realities. For example, he says that stating *the chair is black* is reductionist, because the chair is certainly many more things than just *black*. It might, all at once, be *shiny*, *tall*, *wooden*, *art-deco*, *fragile*, *worn*, *hand-made*, *slightly chipped at the bottom of one leg*… well, you get the point.

And that's an interesting point to make, philosophically speaking. Applied to software design, we could take it as an advice for considering problems holistically, with a fine understanding of their very details. However, I would argue that, conversely, beyond being able to see things as they really are, your role as a software developer, designer or architect is precisely to break up and reduce such complexity into smaller conceptual chunks.

Not being gifted with Gilbert Gosseyn's second brain, we need to dissect, simplify and distil a potentially infinite reality into much less exhaustive - though workable - *abstractions*.

# But what exactly *is* abstraction?

Formally, *abstraction* comes from the Latin *abs* (away from) and *trahere* (to draw) and is the reduction of something to a set of essential characteristics. But let me try and put it in a very code-centric way:

> An abstraction is a simplified representation of some entity, purposefully chosen for a specific context, allowing another entity to relate to it, without yet coupling them together.

Whoa! That's a lot to take in at once, so let's take it apart...

## It is a simplified representation, not the actual thing itself

An abstraction does not (nor should it try to) capture the entity as a whole, in all its capabilities and glory. It only represents a very limited subset of its characteristics.

Take your fridge's light switch. It is a representation of the door's actual *open* or *close* state, allowing the light to turn on or off, along with the door opening or closing. But it's really just a representation of that concept — *not the real thing*.

As a kid, I'm sure you must have enjoyed fooling the fridge into thinking the door was closed by pressing your finger against the switch (yeah right, tell me you never did!)

Just consider for a moment how much more complex it would be, from an engineering point of view, to let the fridge know *for sure* whether its door is open or close. Luckily, the switch abstraction is just good enough!

## It is context-specific

Okay, it's just a subset of characteristics, however, our choice of characteristics depends on the *context* (in other words, the *intention* or *purpose*).  Completely different subsets might be drawn from the same entity in different contexts.

>  Take *Liam*, some lovely fictitious human being, and see the various abstractions he exposes, in different contexts (in the form of C# interfaces!) While he boasts an `ICertifiedPublicAccountant` interface, which is the only one his boss cares and wants to know about, his colleagues particularly appreciate his `IFoosballPlayer` interface at lunch-time, his friends rely on his `IListener` interface and his kids crave his `IPancakeMaker` interface on Sunday mornings and his `IStoryteller` interface at bed-time, among so many others. All without mentioning his secret `IBestLoverUnderTheSheets` interface, but that one solely reserved to his wife's benefits.

## It allows things to relate

An abstraction is intended to *connect* two different parties. It provides a clean and straightforward channel for them to discover each other, connect and, typically, communicate and interact together.

In the real and virtual worlds, those two parties and the abstraction between them can take on different names, such as client-(API)-server, consumer-(contract)-service, subscriber-(subscription)-publisher, employer-(job title)-employee, listener-(speech)-speaker, usage-(interface)-implementation…

> Take the `IWebDeveloper` job title. That is a very handy abstraction. It allows a developer to advertise what he is able to achieve (he *implements* that interface) and an employer to advertise an available position (it *consumes* or has a *dependency* on that interface).  Now, imagine what would happen if we were to remove abstractions altogether and try to interact only with whole realities. The employer could not simplify things down to a straightforward job description; it would need to describe precisely *everything* the employee might be required to do in a day. And the employee, on the other end, would need to describe *everything* that constitutes what he is as a person.

## Yet keeps them independent

Abstraction allows entities to keep some healthy distance from each other, by avoiding their respective implementation details from becoming entangled and dependent.

When entities know each other only via abstract interfaces, we say they are *loosely coupled*, as opposed to entities that depend on specific other entities and their implementation details, which would be *strongly coupled*.

Of course, both the consuming and the implementing entities depend upon the abstraction itself — that is how they can relate. However, they don't depend directly upon one another.

Actually, that is precisely what the [dependency inversion principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle) states:

> High-level modules should not depend on low-level modules. Both should depend on abstractions.

That loose coupling introduces an unlimited world of flexibility and possibilities, which brings us to our next point…

## It allows to replace, impersonate, intercept, observe, delegate…

Swell! Sounds like a riveting *John le Carré*'s espionage novel, where you never know who you (really) are talking to, and how the information you provide will be used. But, as opposed to espionage, in software development that is actually the key to flexible and reusable designs and is essential to approaches like dependency injection and to most design patterns, such as the *strategy*, *proxy*, *decorator* and *composite*.  More on those (exciting!) topics in a later post.

## Humans create abstractions (all the time)

We thrive on abstractions, whether they be physical, virtual or merely conceptual. They are at the core of science, technology, society and progress. We sometimes refer to them as interfaces, protocoles, standards, contracts, languages, idioms, job titles, buttons, etc.  Without them, we could not accomplish much.

But, let's not tap ourselves in the back just yet. Humans are not the ultimate inventors of abstraction.  It has existed long before we came to crawl this earth.

## Nature creates abstractions (for the same reasons we do)

Anything that interfaces between two parties, while conveying some kind of meaning is a form of abstraction. There are countless examples in nature and in our body. For example, enzymes rely entirely on abstractions when they need to interact with substrates. They expose *binding sites* with very specific electrostatic conformations/shapes (we could say *they consume specific interfaces*). Substrate molecules have corresponding  conformations (*they implement those interfaces*), allowing them to snap into binding sites and undergo chemical reactions.

<img src="/images/diagrams/enzyme-binding.png" alt="Enzyme Binding" style="height: 450px"/>

Enzymes relate to substrate only through the abstraction of their electrostatic conformations. They could not tell the substrate apart from another molecule with the same conformation. And that is exactly what we take advantage of to create inhibiting drugs, which expose the same conformation as some substrate and prevent it from being processed by binding with the enzyme in its place.

<img src="/images/diagrams/inhibiting-drug.png" alt="Inhibiting Drug" style="height: 450px"/>

Our immune system also relies on abstractions. Instead of having to memorize the infinitely complex structures of disease agents, it simply focuses on their signatures (*interfaces*).  Vaccines leverage that abstraction, by mimicking disease agents (*implementing the same interface*) and stimulating the immune system to build defenses against them. 

## Abstractions in C# #

Most programming language constructs are forms of abstraction.

In C#, interfaces, methods, delegates and lambdas all expose some operations that can be invoked, while isolating the *who* wants that to happen (and *why* and *when*) from *how* it will happen.

## The interface segregation principle (or *small is beautiful*)

Our friends at [Wikipedia](https://en.wikipedia.org/wiki/Interface_segregation_principle) have this to say:

> The **interface-segregation principle** (**ISP**) states that no client should be forced to depend on methods it does not use. ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them. […] ISP is intended to keep a system decoupled and thus easier to refactor, change, and redeploy.

More concisely, I would say:

>  Smaller interfaces are easier to implement, consume and understand and, as such, are more usable, reusable, flexible and pluggable.

### Complexity vs flexibility

I would dare advance that, generally speaking:

> The level of abstraction of an interface is *inversely* proportional to its complexity.

That complexity can be roughly measured as a function of the number of members it contains, as well as the number and complexity of parameters in its methods.

In other words, the power of an interface resides in its simplicity. Small *is* indeed beautiful.

One of the simplest — almost deceivingly simple — interfaces in the CLR is `IDisposable`, which only exposes a single `Dispose()` method without parameters. It is not, in itself, rich or expressive, however it is precisely *that* simplicity which makes it so powerful. Hundreds of CLR types implement it, the `using` statement leverages it, and even ReactiveX has elected it as the tool of choice for unsubscribing from arbitrarily complex chains of observables. It is so useful that I will most probably dedicate an entire post to it in the future.

> The most abstract interface, however, would be an empty one, without any method or property, whose sole presence on a type is sufficient to convey meaning. Such constructs are called *marker interfaces*, because they mark a type as requiring special treatment, whatever that means in that context.

That idea of minimalism and simplicity will become crucial when we will approach Fluent APIs in a future post and see how to create concise and expressive syntaxes using decorators and extension methods.

### Keep implementation details out

Nevertheless, keeping an interface small and simple is not sufficient in itself to make it more abstract and reusable. There are other factors that come into play. So I would add that:

> Everything that relates to implementation details should be kept out of an interface.

That includes dependencies, configuration data and constants (and basically anything that would probably be irrelevant if you were to reimplement that interface entirely differently). These implementation details are better passed into the constructor and stored as immutable data (typically in read-only private fields). We will eventually come back to that, because that's a very important and often overlooked subject.

### About SOLID principles

The *dependency inversion* and *interface segregation principles* are only the *D* and *I* of the five [S.O.L.I.D. principles](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)), which are at the core of understandable, flexible and maintainable software design. If you don't know them already, I strongly recommend you take the time to learn about them and try to put them into practice as much as possible in your projects. More on those in future posts.

# Conclusion

I believe that the mastery of navigating levels of abstraction and constantly figuring what is truly relevant in every given situation is probably one of the most important skills a programmer could develop throughout his/her career.

In this blog, I will share my thoughts and findings on all sorts of software development topics, from patterns to best practices, through technologies and frameworks, but most of the time with abstraction as an underlying thread.

My next post, I promise, will shift from this very high, philosophical level, to the much lower and more concrete level of C#. More precisely, what abstraction levels are built into C# and how to take advantage of them.

Maybe that Van Vogt's message - as opposed to being interpreted as saying abstractions are bad - should simply help us illuminate how much they are present in our daily lives, how much we rely on them for even the smallest things we do, yet keeping in mind that reality is vastly richer and endless. 

In the meantime, go on, contemplate the numerous abstractions that surround us and, next time someone asks you where to sit, simply reply *the black chair*.
