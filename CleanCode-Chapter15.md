# Chapter 15 - JUnit Internals

Uncle Bob selects ComparisonCompactor class as an example and he tries to refactor it. I think the idea behind this chapter is encouraging people to do refactoring. As you may guess before starting refactor, he says that ComparisonCompactor class has %100 test coverage which is vital for refactoring process.

All my refactoring I did during my career was over the code which had %0 test coverage. Because of this doing refactor is always in an anxious manner for me. After each change, you may need to test the behaviour. If there is no written test, the project may need to be retested to the most comprehensive range.

He starts refactoring with renaming member names, encapsulating conditionals, avoiding from negative conditionals and renaming method names. All of this kind of work can be considered as small examples of refactoring. He reverses some of his decisions during refactoring. He says that often one refactoring leads to another that leads to the undoing of the first. Refactoring is an iterative process full of trial and error, inevitably converging on something that we feel is worthy of a professional. So we need to trust ourselves during this process. Nothing is perfect!

Refactoring is a frequently used and respected word in software development. Since its respected developers generally imagine it as impossible to reach. They don’t trust themselves.

However, Uncle Bob states that its a philosophy to make the world better just like Robert Stephenson Smyth Baden-Powell, the father of scouting, says “Try and leave this world a little better than you found it”. He converts this sentence to: “Always check a module in cleaner than when you checked it out.”.

Refactoring is set to simple rules and please don’t avoid these rules. He lastly says that “Caring for our own code is one thing. Caring for the team’s code is quite another. Teams help each other and clean up after each other. They follow the Boy Scout rule because it’s good for everyone, not just good for themselves.”
