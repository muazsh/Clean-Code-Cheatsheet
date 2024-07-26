# Clean Code Cheatsheet

Here is a summary of  **Clean Code** book by *Robert Cecil Martin*, followed by additional guidelines for a cleaner code:

## General Rules
-	So if you want to go fast, if you want to get done quickly, if you want your code to be easy to write, make it easy to read.
-	The Boy Scout Rule: Leave the campground cleaner than you found it.
-	Meaningful Names:
```
o	Use Intention-Revealing Names: The name of a variable, function, or class, should answer all the big questions.
o	Classes and objects should have noun or noun phrase names.
o	Methods should have verb or verb phrase names.
```
- Follow one naming convention.
- Follow a unified format for indentations, whitespaces, parentheses, new lines, grouping,..., I prefer to use a tool to do that like `Clang Format` or `Visual Studio Format`. 
- Prefer polymorphism to if/else or switch/case as it reduces branching in the code.
- Prefer Exceptions to Returning Error Codes as it requires immediate handling, and if statements.
- Extract Try/Catch Blocks in functions as they introduce noise in the main context.
- Continuously refine and refactor your code and keep it as clean and simple as it can be. Never let the rot get started.
- Follow Kent Beck’s four rules of Simple Design:
```
o	Run all the tests: a comprehensively tested system is verifiable and can be deployed, making such system pushes toward having small classes and applying SRP (Single Responsibility Principle) and DI (Dependency Injection).
o	No duplication: a primary enemy of a well-designed system.
o	Expresses the intent of the programmer (small classes/functions, good names, follow standards, tests )
o	Minimizes the number of classes and methods: No conflict here, not all classes need interfaces and not all object classes must be separated into data classes and behaviour classes.
```
## Functions:
-	FUNCTIONS SHOULD DO ONE THING. THEY SHOULD DO IT WELL. THEY SHOULD DO IT ONLY.
-	Arguments the less the better (different abstraction level form function).
-	Do not return or pass null.
## Classes:
-	Hide internal state and expose methods.
-	Data/Object: In any complex system there are going to be times when we want to add new data types rather than new functions. For these cases objects and OO are most appropriate. On the other hand, there will also be times when we’ll want to add new functions as opposed to data types. In that case procedural code and data structures will be more appropriate.
-	Law of Demeter: minimize coupling.
-	Separation of Concerns: Using design patterns and dependency injection for example helps applying this principle.
## Comments:
-	Comments must **not** be for explaining complexity of code rather the code should explain itself. 
-	Good comments describe some technical aspects or returned value, TODO comments, showing the importance of stuff that do not seem to be.
-	Do not comment out code, delete it.
## Tests:
-	Tests are as important as the project (If you let the tests rot, then your code will rot too. Keep your tests clean).
-	Test code should be as clean as production code (readable).
-	The higher the test coverage the less your fear.
-	One test should test one concept.
-	Minimize asserts in one test.
-	Tests must be **Fast, Independent, Repeatable, Self-Validating, Timely** ( just before the production code).
## Third-Party Packages:
-	Do not expose third-party interface to you APIs, use them only internally.
- Make a wrapper around a third-party library better than exposing the library itself everywhere.
- Test third party packages.
## Concurrency:
-	Keep your concurrency-related code separate from other code.
-	Use what language might offer before making yours.
-	Keep synchronized sections small
-	Think about shut-down early and get it working early.
-	Testing threaded code:
```
o	Treat spurious failures as candidate threading issues.
o	Get your nonthreaded code working first.
o	Make your threaded code pluggable.
o	Make your threaded code tunable.
o	Run with more threads than processors.
o	Run on different platforms.
o	Instrument your code to try and force failures.
```
#
That was my summary of Clean Code book and here are more guidelines for a cleaner code:
## Implementation Principles:
- KISS (Keep It Simple Stupid): Avoid any unnecessary complexity.
- DRY (Don`t Repeat Yourself): As mentioned previously.
- YAGNI (You Aren`t Gonna Need It): Do not write code because you think you gonna need it.
## Design SOLID Principles:
- Single Responsibility: Any function must have one job, any class must have one concept, also modules and libraries must introduce services in one context.
- Open-Close Principle: Entities (classes, modules, libs) must be open for extension but not for modification.
- Liskov Substitution Principle: Replacing an object of a class by another one of a class derived from that class must not lead to errors in the program behaviour.
- Interface Segregation Principle: Introducing multiple interfaces each one includes functions of one service and pass them to the client on demand is better than introducing an interface with many functions some of them the client never needs.
- Dependency Injection: This reduces the coupling in a great deal, so instead of creating the needed objects internally to get some service, just pass that service.
## More
- Use the design patterns once applicable.
- Avoid Anti-Patterns, those bad habits which seem to resolve issues like having GOD class.
- Avoid code-smells, things that cause confusion while code reading like, a function with many parameters, bad names, magic numbers,...
- Use a static code analyser like CppCheck and Resharper. 
