---
layout: post
current: post
cover:  assets/images/covers/jussara-romao-335086.jpg
navigation: True
title: Abstraction, "the Chair is Black" and What you Could do with a Second Brain
class: post-template
subclass: 'post tag-getting-started'
author: mathieu
categories: welcome mathieu
typora-root-url: ../assets
---

*In this post (my first blog post ever!), we will first have a look at abstraction — what it is, how it works and where to find it when you go shopping — and then go through a few principles and best practices of how to apply it in your software design. Some concepts will be introduced that I will be deepening in following posts.* 

I recall as a teenager being totally absorbed by a great 1948 sci-fi novel written by A. E. Van Vogt entitled [The World of Null-A](https://en.wikipedia.org/wiki/The_World_of_Null-A), in which the amnesic main character, Gilbert Gosseyn, discovers he has grown a second brain allowing him to memorize scenes with extreme detail and precision. He later teleports himself to these places by simply evoking photographic memories. He discovers that perceiving things in their finest detail is the secret art of *non-Aristotelian logic*, mastered solely by the peaceful and discreet detective people of Venus.

As I remember, Van Vogt explains that, according to *non-Aristotelian logic*, objects should not be reduced to their simplest attributes but rather considered as rich and vastly complex realities. For example, stating that "*the chair is black"* is reductionist because the chair is certainly many more things than *black*. It might, all at once, be *shiny*, *tall*, *wooden*, *art-deco*, *fragile*, *worn*, *hand-made*, *slightly chipped at the bottom of one leg*… well, you get the point.

This is certainly an interesting point to make, philosophically speaking. Applied to software design, we could interpret it as advice on how to consider problems holistically, with a fine understanding of their every detail. Conversely, I would argue that beyond being able to see things as they really are, your role as a software developer, designer or architect is to break up and reduce such complexity into smaller conceptual chunks.

Since we aren't gifted with Gilbert Gosseyn's second brain, we must dissect, simplify and distil a potentially infinite reality into much less exhaustive, though workable, *abstractions*.

# What exactly *is* abstraction?

Formally, *abstraction* comes from the Latin *abs* (away from) and *trahere* (to draw). It is the reduction of something to a set of essential characteristics. That said, let me try to put it in a very code-centric way:

> An abstraction is a simplified representation of some entity, purposefully chosen for a specific context, allowing another entity to relate to it, yet without coupling them together.

Whoa! That's a lot to take in at once, so let's take it apart...

## It is a simplified representation, not the actual thing

An abstraction does not (nor should it try to) capture the entity as a whole, in all its capabilities and glory. It only represents a very limited subset of its characteristics.

Take your fridge's light switch for example. It represents the door's state; the light turning on or off depending on whether the door is opened or closed. However, it's really just a *representation* of that state — *not the real thing*.

<img src="/images/diagrams/abstraction-fridge-light-switch.jpg" alt="Fridge Light Switch" style="height: 250px"/>

I'm sure, as a kid, you must have enjoyed fooling the fridge into thinking its door was closed by pressing your finger against the switch (yeah right, tell me you never did this!). This was only possible because the switch was not the actual state, just a mere representation of it.

Consider for a moment how much more complex it would be, from an engineering point of view, to let the fridge *really* know whether its door is opened or closed. Not only would devising such a mechanism be incredibly complex but, unless you are targeting the high-security fridge market, it would also be considered overkill and would *still* rely on some form of abstraction or another.

Interestingly, the switch abstraction is probably the simplest and most efficient abstraction that works in that context.

## It is context-specific

While an abstraction is limited to a subset of characteristics, our choice of precisely *which* ones depends on the *context* (in other words, a specific *intention* or *purpose*). Completely different characteristics might be drawn from the same entity in different contexts.

> Take *Liam*, a lovely and complex fictitious human being. While he offers an `ICertifiedPublicAccountant` interface, which is the only one his boss cares for and wants to know about; his colleagues particularly appreciate his `IFoosballPlayer` interface at lunch-time. His friends rely on his `IListener` interface while his kids crave his `IPancakeMaker` interface on Sunday mornings and his `IStoryteller` interface at bed-time, among so many others. All without mentioning his secret `IBestLoverUnderTheSheets` interface, solely reserved for his loved one's benefit.

## It relates things to one another…

An abstraction is intended to relate two entities together. It provides a clean and straightforward channel for them to know about each other and, typically, interact with one another.

In the real and virtual worlds, two entities and the abstraction between them can have different names, such as client-API-server, consumer-contract-service, subscriber-subscription-publisher, employer-position-employee, listener-speech-speaker, usage-interface-implementation, etc.

## …yet keeps them independent

An abstraction allows entities to keep a healthy distance from each other by preventing their respective implementation details from becoming entangled and thus, dependent.

When entities know each other solely via abstract interfaces, we refer to them as *loosely coupled* (as opposed to entities that depend on other specific entities and their implementation details, which are said to be *strongly coupled*). Of course, loosely coupled entities *do* depend upon the abstraction through which they relate, which is exactly what the [dependency inversion principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle) encourages:

> High-level modules should not depend on low-level modules. Both should depend on abstractions.

Such loose coupling introduces an unlimited world of flexibility and possibilities, which brings us to our next point…

## It allows for replacement, impersonation, interception, observation, delegation…

Swell! Sounds like a riveting *John le Carré* espionage novel where you never know who you (really) are talking to, and how the information you provide will be used. However, as opposed to espionage, in a software development context, that opacity is actually the key to flexible and reusable designs. It is essential to approaches like dependency injection and design patterns, such as the *strategy*, *proxy*, *decorator* and *composite*. More on all of these in a later post.

## Humans create abstractions for efficiency

We thrive on abstractions, whether physical, virtual or merely conceptual. They are at the core of science, technology, society and progress. We sometimes refer to them as interfaces, protocoles, standards, contracts, languages, idioms, job titles, buttons, etc. We naturally resort to them because they are efficient.

However, let's not pat ourselves on the back just yet. Humans are not the ultimate inventors of Abstraction, with a capital *A*. It has existed long before we came to crawl this earth.

## Nature creates abstractions (for the same reason humans do)

Nature always takes the straightest, most efficient path. Faced with a problem like our fridge's state, it would most probably settle for a solution as straightforward as our (now famous) light switch.

Take the enzymes in our body, which rely entirely on abstractions when they need to interact with substrates. They expose *binding sites* with very specific electrostatic conformations/shapes (we could say *they consume specific interfaces*). Substrate molecules have corresponding conformations (*they implement those interfaces*), allowing them to snap into binding sites and undergo chemical reactions.

<img src="/images/diagrams/abstraction-enzyme-binding.png" alt="Enzyme Binding" style="height: 350px"/>

### Enzyme binding

Enzymes relate to substrates only through the abstraction of their electrostatic conformations. They wouldn't be able to tell a substrate apart from another molecule with the same conformation. This is exactly what we take advantage of when creating inhibitor drugs, which sport the same conformation as a given substrate, preventing the latter from being processed by binding to the enzyme in its place.

<img src="/images/diagrams/abstraction-inhibiting-drug.png" alt="Inhibiting Drug" style="height: 350px"/>

### Inhibitor drugs

Our immune system also relies on abstractions. Instead of having to memorize the infinitely complex structures of disease agents, it simply focuses on their signatures (*interfaces*). Vaccines leverage these abstractions, by mimicking disease agents (*implementing the same interface*) and stimulating the immune system to build defenses against them.

## The interface segregation principle (a.k.a. *small is beautiful*)

Our friends at [Wikipedia](https://en.wikipedia.org/wiki/Interface_segregation_principle) really want us to know that:

> The **interface-segregation principle** (**ISP**) states that no client should be forced to depend on methods it does not use. ISP splits interfaces that are very large into smaller and more specific ones so that clients will only have to know about the methods that are of interest to them. […] ISP is intended to keep a system decoupled and thus easier to refactor, change, and redeploy.

More concisely, I would say:

> Smaller interfaces are easier to implement, consume and understand and, as such, are more reusable, flexible and pluggable.

### Complexity vs flexibility

I would dare state that, generally speaking:

> The level of abstraction of an interface is *inversely* proportional to its complexity.

This complexity can be roughly measured as a function of the number of members it contains as well as the number and complexity of parameters in its methods.

In other words, the power of an interface resides in its simplicity. Small *is* indeed beautiful.

One of the simplest — almost deceivingly simple — interfaces in the CLR is `IDisposable`, which only exposes a single `Dispose()` method without parameters. It is not in itself rich or expressive; however, it is precisely *this* simplicity which makes it so powerful. Hundreds of CLR types implement it; the using statement leverages it; even the designers of Reactive Extensions have selected it as the tool of choice for unsubscribing from arbitrarily complex chains of observables. It is so useful that I plan on dedicating an entire post to it in the future.

The most abstract interface; however, would be an empty one — without any method or property — whose sole presence on a type is sufficient enough to convey meaning. Such constructs are called *marker interfaces*, because they *mark* a type as requiring special treatment, whatever that means in that context.

Those ideas of minimalism and simplicity will become crucial when we tackle Fluent APIs in a future article and examine how to create concise and expressive syntaxes using decorators and extension methods.

### Leave implementation details out

Nevertheless, keeping an interface small and simple is not sufficient in itself to make it more abstract and reusable. There are other factors that come into play. So I would add that:

> Everything relating to implementation details should be kept out of an interface.

That includes dependencies and configuration data (and basically anything that would be irrelevant if you were to re-implement that interface in a different class). These implementation details are better passed into class constructors and stored as immutable data (typically in read-only private fields). We will eventually come back to this, because it is a very important and often overlooked subject.

### About SOLID principles

The *interface segregation* and *dependency inversion principles* are only the *I* and *D* of the five [S.O.L.I.D. principles](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)), which are at the core of understandable, flexible and maintainable software design. If you don't know them already, I strongly recommend you take the time to learn about them and try to put them into practice as much as possible in your projects. More on those in future posts (I know, that's a lot of promises I'm committing to!)

# Conclusion

Developing a sixth sense for what is truly relevant in each given situation versus what should be hidden away as implementation details is probably one of the most vital skills in a developer's toolbox. This will serve as main thread in this blog, while I share my thoughts and findings on all sorts of software development topics — from patterns and techniques to best practices.

Van Vogt enlightens us on how much abstractions are taken for granted and often mistaken for the real thing. Nevertheless, when you design your next exquisite `Chair` class, don't feel bad if its public interface reduces all its sophistication to a mere "*the chair is black!"*