# Week 3 Study Guide

## Day 1

What is a queue as a data structure?

What is a deque?

What is a tree?

What is a binary tree?

What is a heap as a data structure?

What is a map as a data structure?

Give examples of when we might want to use each of the data structures.
- queue
- deque
- tree
- heap
- map

What is the Collections API?

What is the inheritance hierarchy for Collections in Java?

What does the Iterable interface provide?

What is the syntax for an enhanced for loop in Java?

What are the popular Java implementation classes for the List interface?

What are the popular Java implementation classes for the Set interface?

What are the main differences between a List and a Set?

What is an ArrayDeque?

What is a doubly-linked list?

Why is the Map interface not part of the Collections hierarchy?

What is the difference between the HashMap and TreeMap implementations?

## Day 2

What is a functional interface?

What is a lambda?

What is the benefit of using lambdas?

Describe each of the following built-in functional interfaces. Include return type, parameter(s), and a simple example of when you might use it.
- Supplier
- Consumer
- Predicate
- Function
- IntFunction (and other primitive specializations)

What is a method reference in Java?

When might you use method references rather than lambdas?

What is the Comparable interface?

What is the Comparator interface?

When would you use Comparable vs. Comparator?

What are Streams in Java?

What are intermediate operations? Give some examples.

What are terminal operations? Give some examples.

What does the `Stream.reduce` operation do? What are its parameters?

What does the `Stream.collect` operation do? What is/are its parameter(s)?

When would you use collect rather than reduce?

What are Optionals in Java?

What is the benefit of using an Optional?

## Day 3

What is the benefit of Java 8's java.time package?

What does the `LocalDateTime.now` method do?

What are Threads?

What does the `Thread.start` method do? How is it related to `Runnable.run`?

What is concurrency?

What is parallelism?

What is asynchrony?

What does it mean for something to be synchronized, as with the `synchronized` keyword in Java?

Describe the lock/key pattern.

How do we create a custom Thread?

Why don't we want to call the `Runnable.run` method directly?

Why don't we want to override the `Thread.start` method?

What do the `Thread.wait` and `Thread.interrupt` methods do?

What is a thread pool? What is the benefit of this?

What is an Executor?

How do we create a thread pool in Java using an Executor?

What is the executor service design pattern?

What is the difference between runnable and executor service design patterns?

## Day 4

What is the Reflection API in Java?

How do we get a Class object from an object?

How can we get Field and Method objects from an object?

How do we get the modifiers, types, and values of fields using Reflection?

How do we get modifiers and parameters of methods and constructors using Reflection?

How can we invoke methods after getting them using Reflection?

How can we get the types of arrays using Reflection?

What are Enums? How do we create one?

Give an example of when we might want to make an Enum.

What are proxies (or JDK proxies)?

Give some examples of when we might want to use proxies.

## Day 5

What is code coverage?

If we want to increase our code coverage, what are some things we might look for?

What is JaCoCo?

What is API testing?

What is curl?

What is Postman?

What is logging? What is the benefit of using it?

What are the most common logging levels?

What are appenders in our logging configuration?

What is the difference between depth-first and breadth-first searching?

When might we want to use depth-first searching vs. breadth-first?