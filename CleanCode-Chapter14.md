# Successive Refinement

In earlier version of example after making parser capable for boolean values is simple and understandable, however its not well designed. When programmer add features to parse String, integer and other values example seems like one very big class with full of features. Its hard to understand and hard to maintain which we call bad code.

At that point he say stop adding new feature and start refactoring. This point is very important, there is a working bad code and programmer feel like code is full of messy.

Bad code needs refactoring. But there is a problem not all the programs work same after refactoring. Refactoring can cause crash or break features. He say to avoid this we need TDD. He refactor example according to TDD, there is already written tests and he is going with simple increments. He always try to be sure that tests are passing and keep system running at all times.

His approach to clean the example is just divide and conquer, make it simple and make it easy to add new features. Separation of concerns makes the code much simpler to understand and maintain.

Robert Martin disagree with people arguing about time limitations. He say that there is nothing worst than bad code for a project in long-term. Bad team dynamics, bad schedules all the problems can be repaired however bad code might not possible to be repaired.

Always write your code as If developer coming after you is a violent psycopath who knows where you live. TDD make our code more maintainable, more easy to understand. So we can say that there is a fellowship between TDD and clean code.
