---
title: "Software development principles and rules"
description: "Software development principles and rules"
keywords: "SOLID, IoC, KISS, YAGNI, DRY"
lang: "en"
permalink: "software-development-principles"
aliases:
  - "software-development-principles"
---

# Software development principles and rules {\#firstHeading}

## Programming principles

[https://en.wikipedia.org/wiki/Category:Programming\_principles](https://en.wikipedia.org/wiki/Category:Programming_principles)

The **SOLID** ideas are

* The **Single-responsibility principle**: "There should never be more than one reason for a class to change." In other words, every class should have only one responsibility.
* The **Open--closed principle**: "Software entities ... should be open for extension, but closed for modification."
* The **Liskov substitution principle**: "Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it." See also design by contract.
* The **Interface segregation principle**: "Clients should not be forced to depend upon interfaces that they do not use."
* The **Dependency inversion principle**: "Depend upon abstractions, \[not\] concretes."

KISS, an acronym for "**Keep it simple, stupid**!", is a design principle first noted by the U.S. Navy in 1960.First seen partly in American English by at least 1938, the KISS principle states that most systems work best if they are kept simple rather than made complicated; therefore, simplicity should be a key goal in design, and unnecessary complexity should be avoided.

**Inversion of control** (IoC) is a design pattern in which custom-written portions of a computer program receive the flow of control from a generic framework. The term "inversion" is historical: a software architecture with this design "inverts" control as compared to procedural programming. In procedural programming, a program's custom code calls reusable libraries to take care of generic tasks, but with inversion of control, it is the framework that calls the custom code.

**"You aren't gonna need it**" (YAGNI) is a principle which arose from extreme programming (XP) that states a programmer should not add functionality until deemed necessary. Other forms of the phrase include "You aren't going to need it" (YAGTNI) and "You ain't gonna need it".

**Worse is better**(also called the New Jersey style) is a term conceived by Richard P. Gabriel in a 1989 essay to describe the dynamics of software acceptance. It refers to the argument that software quality does not necessarily increase with functionality: that there is a point where less functionality ("worse") is a preferable option ("better") in terms of practicality and usability. Software that is limited, but simple to use, may be more appealing to the user and market than the reverse.

**"Don't repeat yourself"** (DRY) is a principle of software development aimed at reducing repetition of information which is likely to change, replacing it with abstractions that are less likely to change, or using data normalization which avoids redundancy in the first place.

### Zen of Python

by Tim Peters

[https://en.wikipedia.org/wiki/Zen\_of\_Python](https://en.wikipedia.org/wiki/Zen_of_Python)

* Beautiful is better than ugly.
* Explicit is better than implicit.
* Simple is better than complex.
* Complex is better than complicated.
* Flat is better than nested.
* Sparse is better than dense.
* Readability counts.
* Special cases aren't special enough to break the rules.
* Although practicality beats purity.
* Errors should never pass silently.
* Unless explicitly silenced.
* In the face of ambiguity, refuse the temptation to guess.
* There should be one-- and preferably only one --obvious way to do it.
* Although that way may not be obvious at first unless you're Dutch.
* Now is better than never.
* Although never is often better than right now.
* If the implementation is hard to explain, it's a bad idea.
* If the implementation is easy to explain, it may be a good idea.
* Namespaces are one honking great idea -- let's do more of those!

## Glossary

**Object-oriented programming**(OOP) is a programming paradigm based on the concept of objects, which can contain data and code: data in the form of fields (often known as attributes or properties), and code in the form of procedures (often known as methods). In OOP, computer programs are designed by making them out of objects that interact with one another

**Object--relational mapping** (ORM, O/RM, and O/R mapping tool) in computer science is a programming technique for converting data between a relational database and the heap of an object-oriented programming language. This creates, in effect, a virtual object database that can be used from within the programming language.

In programming language theory and type theory, **polymorphism** is the use of a single symbol to represent multiple different types. In object-oriented programming, polymorphism is the provision of a single interface to entities of different types The concept is borrowed from a principle in biology where an organism or species can have many different forms or stages.

In software systems, **encapsulation**refers to the bundling of data with the mechanisms or methods that operate on the data. It may also refer to the limiting of direct access to some of that data, such as an object's components. Essentially, encapsulation prevents external code from being concerned with the internal workings of an object. Encapsulation allows developers to present a consistent interface that is independent of its internal implementation. As one example, encapsulation can be used to hide the values or state of a structured data object inside a class, preventing direct access to them by clients in a way that could expose hidden implementation details or violate state invariance maintained by the methods.

## Opensource

Comparison of free and open-source software licences [https://en.wikipedia.org/wiki/Comparison\_of\_free\_and\_open-source\_software\_licences](https://en.wikipedia.org/wiki/Comparison_of_free_and_open-source_software_licences)

[https://en.wikipedia.org/wiki/List\_of\_free\_and\_open-source\_software\_packages](https://en.wikipedia.org/wiki/List_of_free_and_open-source_software_packages)

## Code review

Code review (sometimes referred to as peer review) is a software quality assurance activity in which one or more people check a program, mainly by viewing and reading parts of its source code, either after implementation or as an interruption of implementation. At least one of the persons must not have authored the code. The persons performing the checking, excluding the author, are called "reviewers" [https://en.wikipedia.org/wiki/Code\_review](https://en.wikipedia.org/wiki/Code_review)

## Artifacts versioning

[https://learn.microsoft.com/en-US/nuget/concepts/package-versioning](https://learn.microsoft.com/en-US/nuget/concepts/package-versioning) (Exampling by Microsoft nuget packages versioning)

A specific version number is in the form Major.Minor.Patch\[-Suffix\], where the components have the following meanings:

* Major: Breaking changes
* Minor: New features, but backwards compatible
* Patch: Backwards compatible bug fixes only
* \-Suffix (optional): a hyphen followed by a string denoting a pre-release version.

Example:

1\.0.1  
6\.11.1231  
4\.3.1-rc  
2\.2.44-beta1

package developers generally follow recognized naming conventions:

* \-alpha: Alpha release, typically used for work-in-progress and experimentation.
* \-beta: Beta release, typically one that is feature complete for the next planned release, but may contain known bugs.
* \-rc: Release candidate, typically a release that's potentially final (stable) unless significant bugs emerge.
