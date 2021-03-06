---
title: "Notes for a Theory of Semantics"
date: 2018-12-18 23:46:24
dp: 14401
featured_image: "/images/header-113.jpg"
images: ["/images/header-113.jpg"]
tags: []
draft: true
---



# Purpose

In this text, I would like to demonstrate something I'm thinking for a few
years: Using programming languages to create more precise descriptions of
philosophical problems. There is an idea called [Literate
Programming](https://en.wikipedia.org/wiki/Literate_programming) advocated by
[Knuth](https://en.wikipedia.org/wiki/Donald_Knuth) but here I'm not eager to
use program itself to **solve** philosophical problems, instead I'll use the
language as a more precise tool to explore the problems.

I'm also using formulas to emphasize what I mean by words. These are by no means
difficult formulas, but in time they may evolve into some kind of calculus for
meaning.

This text is called **Notes for a Theory of Semantics.** It's certainly not a full
fledged theory, though it may touch important ideas here and there and unite
them into a coherent piece.


# Meaning and Mind

If there is a search for meaning in a situation, we can look for three
ingredients:

\[m=M(s, c, r)\]

If \(m\) is the meaning we are looking for, \(M\) is a mind and we need a symbol \(s\)
and this \(s\) should be presented in a context \(c\). There should also be \(r\),
some external reference outside of mind \(M\), so that we can **search** it.


## Existence of \(m\)

The first problem is the **existence** of \(m\).

When a symbol \(s\) is created, it creates a meaning for a **mind.** This meaning
can be expressed with other symbols or not. If I utter a sound \(s_i\), this sound
can be written down with other symbols \(s_j, s_k\) or not.

However if something is a **sign,** then we can agree that it's a **sign of
something** and if there is such a connection, then we can ascribe **existence** to
meaning.

Suppose there is no \(m\), that is there is no meaning that can be presented with
a symbol \(s\). If there is no meaning, then there should be no **need** to produce
a sign \(s\). This sign should be **meaning of itself.** However, even in this case,
we temporally create meaning, that past \(s\) and future \(s\) are references to
itself.

So if there is a sign, there is a meaning. The meaning of a sign may change up
to context, to mind or other factors but the **existence** of meaning is inherent
in the sign.


### Example

Suppose someone tries to produce a sign that doesn't have a meaning. In this
case, the sign will have the meaning that **signs may have no meaning.** Hence if
a sign is put somewhere it certainly has a meaning, even **meaninglessness as a
meaning.**


## Need for a Mind \(M\)

Another problem is the **need for \(M\)** for the emergence of meaning. 

****Do we always need a mind \(M\) for meaning to exist?****

This question is related but different than **can only human mind create a
meaning?** question.

We won't be spending much time about this question, because, by definition
**meaning** always supposes that there is a mind around that makes the connection
with symbol and object \(j\). Can we find an example where meaning exist without a
mind?


## Need for a Context \(c\)

Do we **always** need a context \(c\) to interpret a symbol \(s\)?

A symbol is, by definition, an abstraction from its environment. When you see a
word on a page, you have to abstract it away from its environment. Nevertheless
environment still retains a connection to the symbol by this **abstraction.**

    
    (defun meaning (symbol context)
       (mind symbol context reference))


# Symbol

For a definition for `symbol`, we should keep in mind that: 

-   A symbol is anything that we ascribe **symbolness.** A cloud may be a symbol for
    rain, a stone may be a symbol for path passing next to it, a drawing may be a
    symbol of **something.**

-   A symbol is something we can abstract away with our senses. The symbol should
    be **individualized** from its environment.

-   A symbol has an associated **sense-data.** It should awake something in our
    perception.

```lisp     
    (defun individualize-symbol (sense-data environment)
      ((let ((temporal-boundary (quote (begin end)))
             (spatial-boundary (quote ((top down right left))))
             (internal-state (merge-state (conscious environment) (unconscious environment)))
             (clues-for-indexing (find-clues-for-indexing sense-data)))
       (separated-data sense-data temporal-boundary spatial-boundary))))
``` 

Now we have more problems: 

-   The abstraction (or individuation) of a symbol depends on not only
    sense-data or the external environment, but also the unconscious part of the
    mind. Therefore in order to **interpret** a symbol, one also must be able to
    sense it and have a clue that this is a symbol.

This seems like the classical chicken and egg problem. *Can a person learn if he
doesn't know that knowledge already?* 

**Can a person recognize a symbol if he doesn't already know that it's a symbol?**

Therefore we need to identify two aspects of a symbol. (1) The *symbolness* of
it that shows that it's a symbol. (2) The *meaning* of it, that shows that it
refers to something else.

An illiterate person can understand something is written on a wall. He's able to
separate the symbol from environment, know that there are letters and words in a
book. (Symbolness.) But he may not read it. (Meaning.)

Another example might be the letters of a different writing system. When I see a
text written in Chinese, I understand that it's a text written in another
language, though I cannot decipher its meaning.

We need to separate these two faculties. Even if we don't know the meaning of a
particular word in a language we don't know, we are able to separate it from the
environment successfully. We can even draw (albeit a bit amateurish) the letters
of an alphabet that we just saw. 

In the above `defun` we identified four aspects of individuation: (1) **Temporal
boundary** means the exposition of symbol to the senses should have a *start* and
and *end.* (2) **Spatial boundary** defines that a symbol should be able to be
separated by (virtual) borders. We should be able to *point* it. (3) **Internal
state** says that the agent's internal state should be enabled to individuate the
symbol, e.g. a person should be aware enough to read a word on a sign. (4)
**Clues for indexing** means that there should be some clues, similarities found
in the symbol to be able to *recognize* it. For a Chinese word, for example, I
should at least be able recognize that it looks like previous Chinese text I
have seen.

Are these *functions* enough to individuate a symbol? It's very difficult to
respond to this question, because even our analysis (will) have some gaps. Before
we can have fully *conscious* machines, it's impossible to answer this question.
However we can answer an easier one, showing that these are *necessary* for
individuation.

## Necessity of Temporal Boundary

We will argue that, without a temporal boundary to the symbol, an agent cannot
individuate it from the environment. Air is such a *symbol* where no one notices
it's a symbol. We individuate its changes, movements, temperature etc. but its
very being cannot be interpreted normally (on land) because since we all live in
it, there is no point to *individuate* it. 

If an agent doesn't experience the *inexistence* of a symbol, she also cannot
experience the *existence* of it. An eye that only sees the light and doesn't
know the darkness cannot see the light.

## Necessity of Spatial Boundary

*Spatial boundary* is required for a symbol because without it, an agent
cannot extract it from the environment. Suppose a city planner built the
city, so that the streets are actually letters of his name. Without any
aerial device or map, people won't notice this symbol.

Suppose our Solar System is one of the corners of a perfect cube that some
alien civilization built, they have embedded their *religious sign* cube to
this artifact and other corners of the cube are also *special planets.* Since
we are *inside* the cube and cannot see this on a *map* we are not able to
*understand* the meaning.


## Necessity of a Suitable Internal State

*Internal state* is the **variable** that we assign to a person's thoughts and
feelings. These are actually quite large, maybe the largest component for
semantics.

We have two kinds of internal state: Conscious and unconscious. The conscious
part is the small one and unconscious is the larger, much larger component. 

Intepreting a symbol needs an awake conscious state that's *connected* with
the symbol, though interpretation usually brings thoughts and feelings from
the unconscious part.

Therefore we need two components and a `merge` for them. 


## Necessity of Resemblance and Clues for Indexing

A symbol and an interpretation are two distinct ideas and as they are
distinct, we need some way to connect these two. 

In general interpretation is this connection, though a symbol should have
some *resemblance* to other symbols to have some interpretation. This
*resemblance* is mostly partial, a symbol partially resembles another symbol,
so it should have some parts that's *identical* to other parts. (Though these
parts may not be described/shown on the symbol. 

For example there is no single part that resembles each other in 我 and 人,
but the *style* of these symbols resemble each other. This style, though
cannot be individuated from the symbols, is a *part* of the symbol, not whole
of it.



## Questions


### What's the role of conscious and unconscious in interpretation?

A mind **should have** at least two components. Otherwise it becomes near to
impossible to apply a reasoning for the *process of interpretation.*

Suppose we a have a singular, monolithic mind. If we consider that all
interpretation happens in this monolithic mind, then we cannot answer the famous
Platonian paradox: How can we interpret a sign if we already don't know its
interpretation?

Answering this paradox requires a modular or composite understanding of mind.
Mind's interpretation process brings clues from **conscious** mind to
**unconscious** and retrieves past **senses** or **memories.** These memories/senses
are merged in the conscious mind with the symbol at hand to get an
**interpretation.**

Mind has an active role in interpretation, it doesn't just associate symbols
with their meaning, it decomposes symbols, finds clues that can be used to
retrieve past experiences and modifies these experiences and symbol at hand to
**generate** a meaning.

In general I consider understanding as the **morphing** of mental imagery with
the sensory data currently in conscious. Suppose unconscious is composed of
mental imagery such as \(U=u_1, u_2, ..., u_n\) and conscious mind has \(C=c_1,
..., c_m\). Understanding means morphing \(u_i\) with \(c_k\) so that these
imagery becomes a connected, coherent piece with \(u_i\).

This is a model somewhat similar to **graph theoretic models** of knowledge
representation. However there are two graphs, \(U\) and \(C\) and both are changing.
\(U\) has millions (or billions) of nodes, \(C\) is limited in this, though when we
think we understand something, it becomes a member of \(U\) and can be retrieved
to \(C\) when necessary.


### How to merge conscious and unconscious?

Suppose we have $c$ mental elements that we can manage to use our attention.
*Attention* is directing conscious mental imagery of conscious mind $C$ with
these elements. However elements of $C$ are connected to their counterparts in
unconscious mind $U$. 

An element $c_i$ of consciousness is related to element $u_j$ of unconscious
mind such that the unconscious neighborhood of $u_j$ is also relevant to
interpreting the symbol in $c_i$. The meaning of the symbol $s_i$ present in
$c_i$ is dependent to neighborhood of $c_i$ and $u_j$. When we say we understand
something we can manage neighborhood of $u_j$ and bring them to our attention
whenever needed. Therefore understanding a symbol is actually bringing its
*unconscious mental neighbors* to *conscious mental elements* as we need. 

We could consider conscious mind as a flashlight that illuminates the *dungeons*
of *unconscious mind* but the

### How two symbols resemble each other?


### How indexing is done in conscious and unconscious?


# Sensation and Perception


# Context and Framing


# Intention and Meaning Space


