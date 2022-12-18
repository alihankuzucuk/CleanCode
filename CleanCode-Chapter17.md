# Chapter 17 - Smells and Heuristics

Code smells are something my mentors here at 8th Light have been warning me about since I started my SnowMan project. I personally do not have the instinctive nose as do they, so I decided that I am going to make a quick cheat sheet with those that are listed in the book.

<table>
  <thead>
    <tr>
      <th>Code Smell / Heuristic</th>
      <th>Description</th>
      <th>Refactoring</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong><em>Comments</em></strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Inappropriate information</td>
      <td>Record keeping or other metadata in source code</td>
      <td>Keep this type of comment in other systems</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Obsolete comment</td>
      <td>Old, irrelevant or incorrect comment</td>
      <td>Delete it, avoid using comments that will become obsolete (or at all)</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Redundant comment</td>
      <td>Comment describes something that would adequately describe itself</td>
      <td>Omit redundant comments, refactor code to be clear</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Poorly written comment</td>
      <td>Comment is not clear about its purpose for writing</td>
      <td>Write understandable comments, brief and to the point</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Commented out code</td>
      <td>Chunks of code not in use but lingering in the source code</td>
      <td>Delete it, it will become obsolete if left long enough</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong><em>Environment</em></strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Build requires more than one step</td>
      <td>Requiring multiple steps to build</td>
      <td>Combine setup to a single command</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Tests require more than one step</td>
      <td>Requiring multiple calls to run all tests</td>
      <td>Reorganize files to call back to a spec runner</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong><em>Functions</em></strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Too many arguments</td>
      <td>Three or more arguments on a function</td>
      <td>Try for zero arguments, add only if necessary</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Output arguments</td>
      <td>Function changes something with an output*</td>
      <td>If the function must change the state of something, have it change the state of its owning object</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Flag arguments</td>
      <td>Boolean arguments hint that the function does more than one thing</td>
      <td>Avoid, break up receiving function to handle two cases</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Dead function</td>
      <td>Methods that are not called</td>
      <td>Delete and don’t write until they are needed</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong><em>General</em></strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Multiple languages in one source file</td>
      <td>Mixing multiple languages in one file</td>
      <td>Separate languages where possible and practical into their own source file</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Obvious behavior is unimplemented</td>
      <td>Code behaves counter-intuitively</td>
      <td>Descriptive naming that communicates the intent of the code</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Incorrect behavior at the boundaries</td>
      <td>Code behaves counter-intuitively for edge cases</td>
      <td>Test all cases, look for every boundary condition</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Overridden safeties</td>
      <td>Turning off warning and exceptions to get the code to build</td>
      <td>Deal with debugging as it comes up, only override when last resort</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Duplication</td>
      <td>Identical (or closely similar) code appearing over and over</td>
      <td>Replace with better methods, abstractions and polymorphism*</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Code at wrong level of abstraction</td>
      <td>High and low level abstractions appear together</td>
      <td>Separate lower level concepts into derivatives and higher level concepts in the base class</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Base classes depending on their derivatives</td>
      <td>Base classes mentioning derivatives</td>
      <td>Base classes should generally not know about their derivatives</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Too much information</td>
      <td>Wide and deep interfaces that require multiple gestures to get things done</td>
      <td>Limit exposure at interfaces, with fewer methods, variables and instance variables</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Dead code</td>
      <td>Code that is not executed</td>
      <td>Delete dead code if it serves no purpose</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Vertical Separation</td>
      <td>Large vertical scope between declaration and use</td>
      <td>Declare variables and functions close to where they are used</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Inconsistency</td>
      <td>Not following a convention</td>
      <td>Pick a way to do and name things and stick to it</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Clutter</td>
      <td>Anything that is not used or not needed in the code</td>
      <td>Keep code base clean and to the point</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Artifact coupling</td>
      <td>Coupling between two modules that serves no direct purpose</td>
      <td>Take time to figure out where functions, constants and variables belong</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Feature envy</td>
      <td>Using accessors and mutators of some other object to manipulate the data within that object</td>
      <td>Try to have class methods only interact with variables and functions of classes they belong to</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Selector arguments</td>
      <td>Passing code to a function to select the behavior</td>
      <td>Split large functions into smaller functions</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Obscured intent</td>
      <td>Code that is hard to read, intent not clear</td>
      <td>Make intent of code visible to reader</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Misplaced responsibility</td>
      <td>Code appears in the wrong class or interfaces</td>
      <td>Place code where reader would naturally expect it to be</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Inappropriate static</td>
      <td>Static function when should be nonstatic</td>
      <td>Only make a function static if there is no chance it will need to behave polymorphically</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Use explanatory variables</td>
      <td>Large calculations with wide span</td>
      <td>Break calculations up into intermediate values in variables with meaningful names</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Function names should say what they do</td>
      <td>You can’t tell from the call what the function does</td>
      <td>Find better names that express intent</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Understand the algorithm</td>
      <td>Code is thrown together that “works”</td>
      <td>Refactor to a clean and expressive function that is obvious how it works</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Make logical dependencies physical</td>
      <td>Dependent modules make assumptions about the module it depends upon</td>
      <td>Dependent modules should explicitly ask other module for all information it depends upon</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Prefer polymorphism to If/Else or Switch/Case</td>
      <td>Use of brute force switch statements</td>
      <td>Consider polymorphism where you would consider a switch statement</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Follow standard conventions</td>
      <td>Not following normal convention, team-specific styles</td>
      <td>Follow a coding standard based on common industry norms</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Replace magic numbers with named constants</td>
      <td>Leaving numbers in code that represent a specific idea</td>
      <td>Change “magic numbers” to constants</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Be precise</td>
      <td>Ambiguities and imprecision in code</td>
      <td>Make decisions precisely, knowing why the decision was made and how to handle exceptions</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Structure over convention</td>
      <td>Poor design decisions</td>
      <td>Use structures that force compliance</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Encapsulate conditionals</td>
      <td>Context is difficult to understand in conditional</td>
      <td>Extract functions that explain the intent of the conditional</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Avoid negative conditionals</td>
      <td>Conditionals expressed as negatives</td>
      <td>Change methods to return the positive rather than negating a negative</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Functions should do one thing</td>
      <td>Function with multiple sections that perform a series of operations</td>
      <td>Convert large function into several small functions</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Hidden temporal couplings</td>
      <td>Order is not obvious for temporal coupling</td>
      <td>Add extra syntatic complexity to make the temporal coupling explicit</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Don’t be arbitraty</td>
      <td>Unorganized code, unclear intent</td>
      <td>Have a reason for the structure and make sure the structure communicates the reason</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Encapsulate boundary conditions</td>
      <td>Boundary conditions leak all over the code</td>
      <td>Put the processing for boundary conditions in one place</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Functions should descend only one level of abstraction</td>
      <td>Mixing levels of abstraction</td>
      <td>Function statements should be at the same level of abstraction, one level below the operation described by the name of the function</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Keep configurable data at high levels</td>
      <td>Constants expected at high level of abstraction buried in low-level function</td>
      <td>Expose high level constants as arguments to low level function called from high level functions</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Avoid transitive navigation</td>
      <td>Single modules know too much about collaborators</td>
      <td>Make sure modules only know about immediate collaborators and not the navigation map of the whole system</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong><em>Names</em></strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Choose descriptive names</td>
      <td>Names don’t describe intent</td>
      <td>Make sure name communicates what the purpose of the function or variable is</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Choose names at the appropriate level of abstraction</td>
      <td>Names communicate implementation</td>
      <td>Name things to reflect the level of abstraction of the class or function you are working in</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Use standard nomenclature where possible</td>
      <td>Names are not relevant to the project</td>
      <td>Base names on existing convention or usage</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Unambiguous names</td>
      <td>Name does not communicate what the function or variable does/is</td>
      <td>Choose names that make intent clear and unambiguous</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Use long names for long scopes</td>
      <td>Short names that apear over wider scope</td>
      <td>Reserve single letter variables for small, local scopes</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Avoid encodings</td>
      <td>Scope or type information encoded into names</td>
      <td>Keep names free of pollution</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Names should describe side-effects</td>
      <td>Side effects hidden</td>
      <td>Names should describe everything that a function, variable, or class is or does</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td><strong><em>Tests</em></strong></td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Insufficient tests</td>
      <td>Some conditions remain unexplored by tests or calculations unvalidated</td>
      <td>Test everything that could possibly break</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Use a coverage tool</td>
      <td>Relying on manual tests</td>
      <td>Use coverage tool with visual indication of coverage</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Don’t skip trivial tests</td>
      <td>Not testing small aspects of the code</td>
      <td>Test everything!</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>An ignored test is a question about ambiguity</td>
      <td>Not adding a test because something is not understood</td>
      <td>Add commented out or ignored test to question the requirements</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Test boundary conditions</td>
      <td>Not considering all edge cases</td>
      <td>Consider all boundaries and test them</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Exhaustively test near bugs</td>
      <td>Not using extra cauting with testing when a bug is found</td>
      <td>Test functions that have bugs very exhaustively</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Patterns of failure are revealing</td>
      <td>Incomplete test cases poorly organized</td>
      <td>Create complete test cases to diagnose problems</td>
    </tr>
    <tr>
      <td> </td>
      <td> </td>
      <td> </td>
    </tr>
    <tr>
      <td>Tests should be fast</td>
      <td>Slow running tests that won’t get run</td>
      <td>Keep tests running quickly by whatever means necessary (situations will vary)</td>
    </tr>
  </tbody>
</table>
