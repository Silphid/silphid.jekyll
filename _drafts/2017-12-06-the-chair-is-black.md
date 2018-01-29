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

> An abstraction is a simplified representation of some entity, purposefully chosen for a specific context, allowing another entity to relate to it, yet without coupling them together.

Wow, that's a lot to take in at once, so let's take it apart...

## An abstraction is a simplified, context-specific representation, not the real thing itself

An abstraction does not (nor should it try to) capture the entity in its whole, with all its capabilities and glory. It only represents a very limited subset of its characteristics. However, *which* characteristics should be selected depends on the *context* (in other words, the *intention* or *purpose*).  Completely different subsets might be drawn from the same entity in different contexts.

>  Let's take *Liam*, some lovely fictitious human being, and see the various abstractions he exposes, in different contexts (in the form of C# interfaces!) While he boasts an `ICertifiedPublicAccountant` interface, which is the only one his boss cares and wants to know about, his colleagues also appreciate him via his `IFerociousTeamFortressPlayer` interfaces. His friends rely on his `IAmAlwaysThereWhenYouNeedMe` interface and his kids crave his `IRitualSundayMorningPancakeMaker` and `ILovelyBedtimeStoryReader`, among so many others. And, of course, he has a secret `IBestLoverUnderTheSheets` interface, but that one is solely reserved to his wife's benefits.

## It allows things to relate...

An abstraction is intended to *connect* two different parties. It provides a clean and straightforward channel for them to discover each other, connect, communicate and interact together. In the real world, those two parties and the abstraction between them can take on different names, such as client-(API)-server, consumer-(contract)-service, subscriber-(subscription)-publisher, employer-(job title)-employee, listener-(speech)-speaker, usage-(interface)-implementation...

> Take the `IFrontEndHtmlDeveloper` job title. That's a very handy abstraction. It allows a developer to advertise what he is able to achieve (he *implements* that interface) and an employer to advertise an available position (it *consumes* or has a *dependency* on that interface).  Now, imagine what would happen if we were to remove abstractions altogether and try to interact only with whole realities. The employer could not simplify things down to a straightforward job description; it would need to describe precisely *everything* the employee might be required to do in a day. And the employee, on the other end, would need to describe *everything* that constitutes what he is as a person.

## …yet, it also keeps them apart

Abstraction allows entities to keep some healthy distance, by avoiding their respective implementation details to make them dependent upon each other.

When entities know each other only via abstract interfaces, we say they are *loosely coupled*, as opposed to entities that depend on specific other entities and their implementation details, which would be *strongly coupled*.

Of course, both the consuming and the implementing entities depend upon the abstraction itself, that is how they can relate. However, they don't depend directly on one another.

In fact, that is precisely what the [dependency inversion principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle) states:

> High-level modules should not depend on low-level modules. Both should depend on abstractions.

That loose-coupling introduces an unlimited world of flexibility and possibilities, which brings us to our two next points...

## It allows to replace either end



Dependency Injection

Strategies

## It allows to intercept and/or delegate

Decorators

Composites



## Man creates abstractions (because they are useful)

And we sometimes refer to them as interfaces, protocoles, standards, contracts, languages, idioms, job titles, buttons, control panels, etc.

Any kind of interface, physical or virtual, is an abstraction, starting with your remote's *play* button, all the way to your oven's control panel. Even your fridge's light switch is an abstraction of the door's actual *open* or *close* state, allowing the light to turn on or off along with the door opening or closing. And it's really just an *abstraction* of that concept - *not the real thing* - because if you barely open the door, the light won't turn on yet, even if the door is actually *open*. You may also replace the door with any other door, and the light switching mechanism will work just as well. And, as a kid, you surely must have enjoyed fooling the light into thinking the door was closed by pressing your finger against the switch (yeah right, don't tell me you never did!)

## Nature creates abstractions (because they are essential)

Anything that interfaces between two parties and conveys meaning is a form of abstraction. There are countless examples in nature. In our body, nerves carry information in an abstract way. And enzymes rely entirely on abstractions when they need to interact with substrates. They expose *binding sites* with very specific electrostatic conformations/shapes (we could say *they consume specific interfaces*). Substrate molecules have corresponding  conformations (or *they implement such interfaces*), allowing them to snap into binding sites and undergo chemical reactions.

<img src="/images/diagrams/enzyme-binding.png" alt="Enzyme Binding" style="height: 450px"/>

Enzymes relate to substrate only through the abstraction of their electrostatic conformations. The enzymes could not tell the substrate apart from another molecule with the same conformation. And that's exactly what we take advantage of to create inhibiting drugs, with the exact same conformation as some substrate, which it prevents from being processed by the enzyme by binding in its place.

<img src="/images/diagrams/inhibiting-drug.png" alt="Inhibiting Drug" style="height: 450px"/>

## Abstractions in C# #

Most programming language constructs are forms of abstraction.

In C#, interfaces, methods, delegates and lambdas all expose some operations that can be performed, isolating the *who* wants them to be performed (and *why* and *when*) from *who* is actually going to perform them (and especially *how*).

The most powerful and useful form is *interfaces*, so I will especially focus on them.

## The interface segregation principle (or *small is beautiful*)

Our dear friends at [Wikipedia](https://en.wikipedia.org/wiki/Interface_segregation_principle) have this to say:

> The **interface-segregation principle** (**ISP**) states that no client should be forced to depend on methods it does not use. ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them. […] ISP is intended to keep a system decoupled and thus easier to refactor, change, and redeploy.

More concisely, I would say:

>  Smaller interfaces are easier to implement, consume and understand and, as such, are more usable, reusable, flexible and pluggable.

### Complexity vs flexibility

I would dare advance that, as a rule of thumb:

> The level of abstraction of an interface is *inversely* proportional to its complexity.

That complexity can be roughly measured as a function of the number of members it contains, as well as the number and complexity of parameters in its methods.

In other words, the power of an interface resides in its simplicity. Small *is* indeed beautiful.

One of the simplest - almost deceiving - interfaces in the CLR is `IDisposable`, which only exposes a single `Dispose()` method without parameters. It is not, in itself, rich or expressive, however it is precisely *that* simplicity which makes it so powerful. Hundreds of CLR types implement it, the `using` statement leverages it, and even ReactiveX has elected it as the tool of choice for unsubscribing from arbitrarily complex chains of observables. It is so useful that I will probably dedicate an entire post to it in the future.

The most abstract interface, however, would be an empty one, without any method or property, whose sole presence on a type is sufficient to convey meaning. Such constructs are called *marker interfaces*, because they mark a type as requiring special treatment, whatever that means in that context.

### Keep implementation details out

But, alone, keeping an interface small and simple is not sufficient to make it more abstract and reusable. There are other factors that come into play. *Everything that relates to implementation details should be kept out of an interface.*

That includes dependencies, configuration data and constants and basically anything that would probably be irrelevant if you were to reimplement that interface entirely differently. These are implementation details and are better passed into the constructor and stored as immutable data (typically in read-only private fields). I will come back to that in a future post, about the different kinds of public surfaces on a type, because that's a very important and often overlooked subject.

### About SOLID principles

The *dependency inversion* and *interface segregation principles* are only the last two of the five [SOLID principles](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)), which are at the core of understandable, flexible and maintainable software design. If you don't know them, I strongly recommend you take the time to learn about them and try to put them into practice as much as possible in your projects. I will come back to some of those principles in future blog posts.

# Conclusion

I believe that the mastery of navigating levels of abstraction and constantly figuring what is truly relevant in every given situation is probably one of the most important skills a programmer could develop throughout his/her career.

In this blog, I will share my thoughts and findings on all sorts of software development topics, from patterns to best practices, through technologies and frameworks, but most of the time with abstraction as an underlying thread.

My next post, I promise, will shift from this very high, philosophical level, to the much lower and more concrete level of C#. More precisely, what abstraction levels are built into C# and how to take advantage of them.

Maybe that Van Vogt's message - as opposed to being interpreted as saying abstractions are bad - should simply help us illuminate how much they are present in our daily lives, how much we rely on them for even the smallest things we do, yet keeping in mind that reality is vastly richer and endless. 

In the meantime, go on, contemplate the numerous abstractions that surround us and, next time someone asks you where to sit, simply reply *the black chair*.
