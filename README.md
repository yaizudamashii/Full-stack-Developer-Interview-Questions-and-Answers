# Full-stack Developer Interview Questions and Answers

## <a name='toc'>Table of Contents</a>

  * [Architecture](#architecture)
  * [Concurrency](#concurrency)
  * [Java](#java)
  * [General Questions](#general)
  * [WEB](#web)
  * [Javascript](#javascript)
  * [QA](#qa)
  * [Agile, Scrum, XP](#agile)
  * [Other](#other)

#### [[⬆]](#toc) <a name='architecture'>Architecture:</a>
* *Design principles*. ([*DRY*](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself), [*KISS*](https://en.wikipedia.org/wiki/KISS_principle), [*separation of concerns*](https://en.wikipedia.org/wiki/Separation_of_concerns)

|Rule|Description|
|:--|:--|
|[**S**ingle responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle)|A module should be responsible to one, and only one, actor.|
|[**O**pen/closed principle](https://en.wikipedia.org/wiki/Open/closed_principle)|A software artifact should be open for extension but closed for modification.|
|[**I**nterface segregation principle](https://en.wikipedia.org/wiki/Interface_segregation_principle)|Many client-specific interfaces are better than one general-purpose interface.|
|[**D**ependency inversion principle](https://en.wikipedia.org/wiki/Dependency_inversion_principle)|Depend upon Abstractions but not on concretions. This means that each module should be separated from other using an abstract layer which binds them together. Source code dependency points in the opposite direction compared to the flow of control.|
 
  * Pros of *microservices* (The services are easy to replace, Services can be implemented using different programming languages, databases, hardware and software environment, depending on what fits best)
* *Design patterns*.
  * **Creational**: [*Factory Method*](https://refactoring.guru/design-patterns/factory-method), [*Singleton*](https://refactoring.guru/design-patterns/singleton)
   * **Behavioral**: [*Command*](https://refactoring.guru/design-patterns/command), [*Observer*](https://refactoring.guru/design-patterns/observer), [*State*](https://refactoring.guru/design-patterns/state)
* [*REST*](https://en.wikipedia.org/wiki/Representational_state_transfer) (Representational state transfer), [*RPC*](https://en.wikipedia.org/wiki/Remote_procedure_call)
* [*Idempotent operation*](https://en.wikipedia.org/wiki/Idempotence) (The PUT and DELETE methods are referred to as idempotent, meaning that the operation will produce the same result no matter how many times it is repeated)
* *Nullipotent operation* (GET method is a safe method (or nullipotent), meaning that calling it produces no side-effects)
* [*Inheritance*](https://en.wikipedia.org/wiki/Inheritance_(object-oriented_programming)) vs [*Composition*](https://en.wikipedia.org/wiki/Object_composition) (Inheritance - is-a relationship, whether clients will want to use the subclass type as a superclass type. Composition - has-a or part-of relationship).
* Advantages of using *modules*. (reuse, decoupling, namespace)
* Drawbacks of not using [*separation of concerns*](https://en.wikipedia.org/wiki/Separation_of_concerns)
  * Adding new features will take an order of magnitude longer
  * Impossible to optimize
  * Extremely difficult to test
  * Fixing and debugging can be a nightmare (fixing something in one place can lead to something else breaking that seems completely unrelated).

#### [[⬆]](#toc) <a name='concurrency'>Concurrency:</a>
* What is [*deadlock*](https://en.wikipedia.org/wiki/Deadlock)? (Deadlock is a situation in which two or more competing actions are each waiting for the other to finish, and thus neither ever does.)
* [*Deadlock avoidance*](https://www.geeksforgeeks.org/deadlock-prevention). (prevention, detection, avoidance (Mutex hierarchy), and recovery)
* What is [*race condition*](https://en.wikipedia.org/wiki/Race_condition)? (Behavior of software system where the output is dependent on the sequence or timing of other uncontrollable events)
* What is a [*thread-safe*](https://en.wikipedia.org/wiki/Thread_safety) function? (Can be safely invoked by multiple threads at the same time)
* [*Publish/Subscribe*](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern) pattern
* What is the difference between *thread* and *process*? (Threads (of the same process) run in a shared memory space, while processes run in separate memory spaces)

#### [[⬆]](#toc) <a name='java'>Java:</a>
* *Garbage collection*. (G1, Young/Old generation collectors combination examples: PS Scavenge/PS MarkSweep, Copy/MarkSweepCompact)
* What is *generics* and PECS (producer extends and consumer super)?
* What is the difference between <?>, \<Object\>, <? extends Object> and no generic type? [link1](http://stackoverflow.com/questions/8055389/whats-the-difference-between-and-extends-object-in-java-generics) [link2](http://stackoverflow.com/questions/678822/what-is-the-difference-between-and-object-in-java-generics)
* Explain method signature for [Collections.max(...)](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#max-java.util.Collection-), [Collections.fill(...)](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#fill-java.util.List-T-), [Collections.copy(...)](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#copy-java.util.List-java.util.List-), [Collections.sort(...)](https://docs.oracle.com/javase/8/docs/api/java/util/Collections.html#sort-java.util.List-java.util.Comparator-)
* Why are arrays covariant but generics are invariant? [link](http://stackoverflow.com/questions/18666710/why-are-arrays-covariant-but-generics-are-invariant)

#### [[⬆]](#toc) <a name='general'>General Questions:</a>
* [*Polymorphism*](https://en.wikipedia.org/wiki/Polymorphism_(computer_science)) (Variable of type Shape could refer to an object of type Square, Circle... Ability of a function to handle objects of many types)
* [*Encapsulation*](https://en.wikipedia.org/wiki/Encapsulation_(computer_programming)) (Packing of data and functions into a single component)
* [*Virtual function*](https://en.wikipedia.org/wiki/Virtual_function) (Overridable function)
* [*Dynamic binding*](https://en.wikipedia.org/wiki/Late_binding) (Actual method implementation invoked is determined at run time based on the class of the object, not the type of the variable or expression)
* How does [*garbage collector*](https://en.wikipedia.org/wiki/Garbage_collection_(computer_science)) work? (Mark and sweep: mark: traverse object graph starting from root objects, sweep: garbage collect unmarked objects. Optimizations: young/old generations, incremental mark and sweep)
* [*Semantic versioning*](http://semver.org)

#### [[⬆]](#toc) <a name='web'>WEB:</a>
* What is HTTP Strict Transport Security ([*HSTS*](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security))? (Prevents Man in the Middle attacks)
* Browser-server communication methods: WebSocket
* [*Character encoding*](https://en.wikipedia.org/wiki/Character_encoding)
* What is session and persistent cookies, sessionStorage and [localStorage](https://en.wikipedia.org/wiki/Web_storage#Local_and_session_storage)?
* Authentication using cookies, [*JWT*](https://en.wikipedia.org/wiki/JSON_Web_Token) (JSON Web Tokens).

#### [[⬆]](#toc) <a name='javascript'>Javascript:</a>
* this keyword
* differences between == and === (http://dorey.github.io/JavaScript-Equality-Table/)
* closures
* What is *MVC*, *MVP*, *MVVM*?
* What is *promise*?

#### [[⬆]](#toc) <a name='qa'>QA:</a>
* What is *unit test*? (A test that purely tests a single unit of functionality)
* What is *component test*?
* What is *integration test*? (Examine several parts of a system to make sure that when integrated, these parts behave as expected)
* Unit tests advantages?

#### [[⬆]](#toc) <a name='agile'>Agile:</a>
* What is Agile? (http://agilemanifesto.org/principles.html)
  * Individuals and interactions over Processes and tools
  * Working software over Comprehensive documentation
  * Customer collaboration over Contract negotiation
  * Responding to change over Following a plan
* What is Scrum? (Roles: product owner, development team, scrum master. Events: sprint)
* What are the differences between Scrum and Waterfall? ( http://www.leanagiletraining.com/agile/waterfall-versus-scrum-how-do-they-compare/)

#### [[⬆]](#toc) <a name='other'>Other:</a>
* Regular expressions. (Examples)

