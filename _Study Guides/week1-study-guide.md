# Week 1 Study Guide

## Day 1

What is Unix?

Give an example of something you might do which uses all of these Unix commands: `cd`, `ls`, `touch`, `mkdir`

What is Git?

What is the benefit of using Git?

What is a Git repository?

What is meant by "local" and "remote" repositories?

What is Java?

What is the benefit of the JVM?

What does the JVM include?

When would we need the JRE and why? What does it include?

When would we need the JDK and why? What does it include?

What does it mean for a language to have static typing?

What is the benefit of garbage collection?

What is object-oriented programming?

What are the benefits of OOP?

Describe each of the following: maintainability, readability, scalability, extensibility

What are the pillars of OOP?

What are the primitive types in Java in order from smallest to largest?

What is a "literal"? Give an example of assigning an integer literal to a variable.

How is an object different from a primitive in Java?

What is a wrapper?

What is the difference between a class and an object?

What is a constructor? How do we call one?

What are the different types of constructors in Java?

What are modifiers?

What does the `static` keyword do in Java?

What does the `final` keyword do in Java?

What does it mean for a variable to be a constant? How can we enforce that in Java?

What is the difference between the pre-increment and post-increment operators?

What is the difference between `&` and `&&` in conditional expressions?

What is a conditional expression?

What is control flow?

What are the conditional statements in Java?

What are the different types of loops in Java?

Give an example where you might want to use a `switch` rather than `if-else`.

Give an example where you might want to use a `while` loop rather than a `for` loop.

What is the difference between `==` and `.equals`?

What is a class member?

What is a field? Give an example of accessing the `id` field of an object referenced by `myObj`.

What is a method? Give an example of calling the `speak()` method of an object referenced by `myObj`.

What are parameters? What are arguments?

Give some examples of parameters that a method might need in a program.

What is the naming convention of variables, fields, and methods in Java?

What is the naming convention of classes in Java?

## Day 2

What do the `mv`, `cp`, and `rm` Unix commands do?

Give an example of a workflow using all of these Git commands: `add`, `commit`, `clone`, `pull`, `push`

What are GitHub issues?

What does it mean to be a compiled language?

What command runs the Java compiler?

What might be the problem if you get a compilation error?

Which of these has the compiler? (JDK/JRE/JVM)

What is the purpose of packages?

What is the naming convention of packages in Java?

Give some examples of packages you might find in a program.

When do you need to use the `import` keyword?

What is encapsulation?

What does a fully encapsulated class look like in Java?

What are access modifiers?

What are the four access modifiers in Java? Describe each.

What is the difference between `protected` and default/no modifier?

What are the different variable scopes in Java?

What does "scope" of a variable mean?

How is scope different from access with access modifiers?

What is a String?

What does it mean to be immutable?

What mutable alternatives do we have to String? What is the difference between the two?

What is concatenation?

What is an array?

How do I create an array in Java?

Why do arrays have to have a fixed length in Java?

What is a multi-dimensional array? How do I iterate over one?

What is an algorithm?

What is testing?

What is debugging?

What are breadcrumbs when it comes to debugging?

What is a design pattern? Why are they important?

What is a POJO?

## Day 3

What is an IDE? What is the benefit of using one?

What is inheritance?

What is the Object class in Java? How does this relate to inheritance?

What keyword is used for inheritance in Java?

What is abstraction?

What is the difference between control abstraction and data abstraction?

What are abstract methods?

What are the differences between abstract classes and interfaces?

Give some examples of when you might want to use abstract classes vs. interfaces.

What is the inheritance hierarchy for Exceptions in Java?

What is an Exception?

What is an Error?

What are the differences between checked and unchecked exceptions?

How can we find out whether an Exception is checked or unchecked just from the Java documentation?

If I just ran `javac` and got an Exception, would it be checked or unchecked?

How can we handle Exceptions in Java?

What is the difference between using `try-catch` and `throws`?

What does the `finally` block do?

What order do multiple `catch` blocks have to be in? Why?

How do we make a custom Exception?

What is a stack trace? What can it tell us?

Why is it important to get comfortable reading the stack trace?

What is the Scanner? What is System.in?

What is the difference between the Scanner methods `.next()`, `.nextInt()`, and `.nextLine()`?

What is file I/O?

What is the difference between a Reader/Writer and a BufferedReader/Writer?

What are data structures?

Describe a linked list.

What is time complexity?

How can you estimate the time complexity of an algorithm?

What is space complexity?

How can you estimate the space complexity of an algorithm?

What are asymptotic notations?

What is the difference between Big O and Omega notations? Which one do we normally use when talking about time/space complexity?

What is a "brute force" algorithm? What are the pros and cons of this?

What is a sprint?

What is a daily scrum/standup meeting?

## Day 4

What is a branch in Git?

How do you create a branch?

How do you switch to a different branch?

What is a pull request in Git?

Give an example of when you might make a pull request.

What is polymorphism?

What is the difference between static/compile-time and dynamic/runtime polymorphism? Which is method overriding and which is method overloading?

How do we override a method in Java?

How do we overload a method in Java?

What is "coding to an interface"? What is the benefit of doing this?

What is the difference between the variable type and the object type?

What is composition (has-a)?

What is type coercion? When do we see this in Java?

What is covariance in Java? How does it relate to polymorphism?

What is the difference between widening and narrowing?

What are nested types? Why would we use this?

What are local anonymous classes? Why would we use this?

What is an array list?

What happens when you want to add elements to an array list but the array is full?

When would you want to use an array list over a linked list?

What is amortized analysis? Why is this relevant to array lists?

What is recursion?

What are unit tests? What is the benefit of unit testing?

What is a stub in the context of testing?

What is pair programming? What is the benefit of this?

## Day 5

What does DRY mean in OOP?

What are the SOLID principles? Describe each one and its benefits.

What are generics in Java? What is the benefit of them?

How do you restrict what a generic type can be a subtype of (for example, a generic type that must inherit from Number)?

What are wildcards when working with generics? Give an example of when we might use this.

How do I reference my generic type within the class?

What are annotations in Java?

How do we create a custom annotation?

Give an example of an annotation we've seen in Java.

What is the stack in Java?

What is the heap?

What does it mean for Java to be "pass-by-value"? How is this different from pass-by-reference?

What is class loading?

When is an object eligible for garbage collection?

Give an example of some code where an object becomes eligible for garbage collection.

What is a stack as a data structure?

What is JUnit?

What are some annotations we might find in JUnit 5?

What are Assertions?

What actually happens when a JUnit test fails?

What is the benefit of unit testing?

What is Mockito?

What is the benefit of mocking?