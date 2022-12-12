# Chapter 12 -  Emergence

This chapter focuses on Kent Beck’s 4 Rules of Simple Design (which are, strangely, actually 2 rules) that can be instrumental in ensuring that developers create well-crafted software. I’ll cover each in the following sections.

## Simple Design Rule 1: Runs All the Tests

A good program is one that passes all the tests and achieves what it intends to achieve. Simple as that. In other words, you have to be able to walk before you can run.

As noted earlier in the book, testing is essential to writing good code. But it’s more than that.

`“The more tests we write, the more we’ll continue to push toward things that are simpler to test.”`

A system that passes tests is more likely to have small, single-purpose classes, something that the authors of Clean Code have been adamant about implementing.

Testing promotes good code writing habits, and one of the good code writing habits is more testing. It’s a vicious (awesome) cycle.

## Simple Design Rules 2–4: Refactoring

According to the book, we should be stopping to consider refactoring after writing every few lines of code.

This seems a bit aggressive to me, but having a strong test suite in place can help assuage any fears that aggressive refactoring will break the code, so that’s a bit of a relief.

Some elements to consider when refactoring:

- Increase cohesion
- Decrease coupling
- Separate concerns
- Modularize system concerns
- Shrink functions
- Shrink classes
- Renaming variables, functions, and classes

These are just a few of the options available to us, or “how” we can effectively refactor code.

The “why” behind our motivations to refactor form their own list:

- Eliminating Duplication
- Ensuring Expressiveness
- Minimizing the number of classes and methods

## Eliminating Duplication

Most software developers have heard the term “DRY” (Don’t Repeat Yourself). Initially, I thought this was to make sure that code is elegant and efficient, but there is a more practical reason behind this concept. More repetition means more work, more risk and add unnecessary complexity.

One interesting strategy for eliminating duplication mentioned in the chapter was approaching with pseudo-code at first. Writing out what each method should achieve (referred to as the “Template Method” pattern) is an excellent way to remove higher-level duplication and easy to execute.

## Minimize Classes & Methods

This is the least important of the three motivations listed, but always a consideration for those who want to write clean code. The number of classes and methods should be as small as possible, and each should be written with as few lines of code as possible. As mentioned before, this protects the program from risk and also makes future testing and refactoring a lot easier.

## Ensuring Expressiveness

In addition to concision, clarity should be of prominent importance when writing code. If those maintaining your code can understand it, there’s less of a chance that they will make mistakes as they are saddled with maintaining it. Increasing expressivity includes choosing better names for functions and classes, but also by keeping things small. This makes sure things are easy to name and easy to understand.

Using a consistent nomenclature throughout the program also helps to imbue a sense of expressivity. This was a tip I found particularly interesting. Although I have not yet written programs alongside other people, I could see how sharing the same nomenclature for things could quickly become an important means for effecive communication as each contributes their own code to the master branch.

These are all things mentioned in earlier chapters of the book, but it’s interesting to see how they fold directly into the principles of a well designed program. You can even be expressive in the way you write tests!
