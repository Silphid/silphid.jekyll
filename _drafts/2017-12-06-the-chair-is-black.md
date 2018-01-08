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

Van Vogt proposes that, according to *non-Aristotelian logic*, objects should not be reduced to their simplest attributes, but rather considered as rich and vastly complex realities. For example, he says that stating *the chair is black* is reductionist, because the chair is certainly many more things than just *black*. It might, all at once, be *shiny*, *tall*, *wooden*, *art-deco*, *fragile*, *worn*, *hand-made*, *slightly chipped at the bottom of one leg*… well, you get the point.

Indeed. For instance, in software development, cultivating a keen sense of details is definitely a great asset. However, let's face it, we are not gifted with Gilbert Gosseyn's second brain, and neither can we embrace a highly complex system in our mind, all at once. We need to dissect, subdivide and simplify such complexity into manageable pieces, interfaced together through convenient *abstractions*.

## But What *is* Abstraction?

Abstraction, from the Latin *abs* (away from) and *trahere* (to draw), is the reduction of something to a set of essential characteristics.

However, the notion of what should be considered essential highly depends on the *context*. Completely different characteristics might be drawn from the same entity in different contexts.

Take John, our protagonist, comfortably sitting on a long chair on the beach, next to Mary, his loved one, sipping a {NameOfYourFavoriteCocktail} and reading a highly technical 600 page book about 3D programming. Mary raises her brown eyes from her book and asks him about what he is reading. As she is not technically-inclined and, by asking that question, cares more about John himself than the quirks of the third dimension, our hero intuitively abstracts all the maths, vectors and formulas away and simply replies: "A 3D programming book that will complement my professional skills and sky-rocket my career." But now, a little girl with curly hairs who was carving canals in the sand nearby and pourring water into them, just noticed John and also questions him on what he is reading. She is obviously neither tech-savvy nor concerned about John's future, so John abstracts all that away and simply answers: "A very complicated book that will allow me to create games with colourful objects and characters in it." As if the entire beach was conspiring against our hero peacefully reading his book, some tanned and muscular surfer walking by, board tucked under his arm, recognizes John as a former colleague and charges him with a loud and annoying "Hey Buddy! Still reading 3D stuff! What's this one about?" As that guy clearly knows about 3D and couldn't care less about the answer, John abstracts away all but the nitty gritty technical jargon: "It's about vertex and pixel shaders and how to optimize them in the context of photo-realistic real-time rendering." But now, John's patience is tried. He promptly salutes his old colleague, kisses his lover on the forehead and rushes back to his hotel room, asking the doorman not to be disturbed and emphasizing he wants to read quietly. As the doorman politely inquires on what he is reading, John pauses for a second and four hundred fifty milliseconds, carefully chooses the proper level of abstraction for the context and replies candidly: "A book!"

Take Dimitri, some theoritical sample of a human being. He provides a great `IBestHusbandInTheWorld` interface, but which is reserved solely for his wife's usage. He boasts a `ICertifiedPublicAccountant` interface, which is the only one his boss cares and wants to know about. However, his colleagues also appreciate his `IFunnyJokesDuringHappyHours` and `IFerociousTeamFortressGamer` interfaces. His friends rely on his `IAmAlwaysThereWhenYouNeedMe` interface. His kids crave his 



# Where is Abstraction?

Or, should we ask, where is it *not*? 

Societies are defined as abstractions, with governments, institutions, demographics and groups assuming different activities and duties, interacting together through implicit - as much as explicit - rules and conventions.

Companies are built upon abstractions, with every employee being assigned an abstract role (though with a *concrete* job description). All collaborate with each others and circulate information via simplified interfaces, (hopefully) not having to care about the fine details of how their colleagues will then perform their jobs.

To revisit the human relation analogy, just consider a moment the various inter*faces* we present to the different people in our life: bosses, coworkers, friends, parents, kids, siblings, lovers. We very selectively abstract away a lot of details about ourselves and present people only what is meaningful and useful to the specific kind of relationship we have with them. And we do that not because we are secretive, but really because it just wouldn't work otherwise.

However, abstraction is not just some clever human invention. It is actually omnipresent in the universe and is essential to the formation of any complex system out of simpler ones.

Think about our body. Organs are not all linked up together nor do they need to know about everything that is happening in our body. Conceivably, our pancreas does not care about our current heartbeat rate, but should clearly be well informed on our blood sugar level. Each organ has very specific (though numerous) abstract interfaces with the rest of the body in the form of veins, nerves, hormones and enzymes, that convey only the essential set of information for it to perform its duty.

And if we zoomed down to the cellular, molecular, atomic and sub-atomic levels, we would certainly find the same ubiquitous abstraction pattern repeating itself over and over.

# Conclusion

I believe that the mastery of navigating levels of abstraction and constantly figuring what is truly relevant in every given situation is probably one of the most important skills a programmer could develop throughout his/her career.

In this blog, I will share my thoughts and findings on all sorts of software development topics, from patterns to best practices, through technologies and frameworks, but most of the time with abstraction as an underlying thread.

My next post, I promise, will shift from this very high, philosophical level, to the much lower and more concrete level of C#. More precisely, what abstraction levels are built into C# and how to take advantage of them.

In the meantime, go on, contemplate the numerous abstractions that surround us and, next time someone asks you where to sit, simply reply *the black chair*.
