# Chapter 16 - Refactoring SerialDate

In this chapter Uncle Bob refactors SerialDate class in JCommon library. SerialDate class includes professionalism and discipline inside it. And Uncle Bob considers it as “good code”. However, he states that each code may have issues even if written by him. He states that reviewing the code of another people and finding errors is not an indication of hierarchy.

He states that “What I am about to do is nothing more and nothing less than a professional review”.

From my understanding this chapter has mentions about psychological aspects of code review. He states that code review process needs to be done kindly and professionally. In addition, every developer should be open to code reviews.

> Uncle Bob states that only through critiques can help us to learn, like doctors, pilots and lawyers do it.

First of all he use Clover to check unit test coverage and the result is approximately %50. Then he wrote unit tests to understand code well and increase coverage. He comment out some of his tests and decide to work on them in refactoring process. After test implementation finish Clover reports that test coverage is %92 even if there is also uncommented tests.

## Refactoring Approaches

- If there is code with only used from test delete test and code together.
- If algorithms a bit complicated try to use EXPLAINING TEMPORARY VARIABLES approach. This approach uses temporary variables to explain more detail about implementation.
- If enum's are pretty large just move it to another class. And implement necessary methods inside enums.
- Connect multiple if statements into a single if statement using the || and && operators.
- Convert constant static integers to enums. (This might be bad for Android)
- Use the power of IDE. Check the usages of variables and methods and replace their names with help of IDE.
- If variable names are sufficient, delete the comments. If not rename variables and methods.
- Name methods and variables meaningful.
- It’s generally a bad idea for base classes to know about their derivatives. To fix this, use the ABSTRACT FACTORY pattern and create instance from factory.
- Delete change history from top of the class because its not important since we are using version control tools.
- Having more than one language in source code causes trouble. Remove html codes from Javadocs.
- Try to understand with why questions.
- Inheriting from classes with constants is an old trick that Java programmers used so that they could avoid using expressions like MonthConstants.January, but it’s a bad idea.
- Redundant comments are just places to collect lies and misinformation. Get rid of them.
- Eliminating final flies in the face of some conventional wisdom. For example, Robert Simmons strongly recommends us to “. . . spread final all over your code.” Clearly I disagree. I think that there are a few good uses for final, such as the occasional final constant, but otherwise the keyword adds little value and creates a lot of clutter.
- Calling one method from another with only a flag generally a bad practice. Make different methods if necessary rather than flag passing.
