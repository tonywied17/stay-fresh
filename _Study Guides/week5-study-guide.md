# Week 5 Study Guide

## REST

What is REST?

What does it mean to have a "representation" of state/resources?

What are the six constraints of REST?

What does uniform interface mean?

What is the naming convention for REST endpoints?

What format can resources be sent in with REST?

What transfer protocols can be used with REST?

What is JSON?

## Spring

What is Spring?

What is a framework?

What does it mean for a framework to be lightweight?

What is IOC?

What is the IOC container?

What is dependency injection?

What are the different types of dependency injection?

What is a Spring bean?

What are the 4 main stereotypes?

What are the main bean scopes?

What annotation do we use for dependency injection in Spring?

What does the `@Bean` annotation do?

Why use constructor injection? When might setter injection be better?

What are the benefits of dependency injection?

What are the differences between the ApplicationContext and BeanFactory?

If using XML configuration, what are some tags you might find in beans.xml?

What is the difference between a Spring project and a Spring module?

## Spring Boot

What is Spring Boot?

What is the main philosophy behind Spring Boot?

What is the configuration file for a Spring Boot application?

What website can you use to generate a base Spring Boot project for you?

What is Spring Boot DevTools?

What is the actuator?

What are Spring Boot profiles? How could this be useful in a test environment?

## Spring MVC

What is Spring WebMVC?

How is it different from Javalin as far as your code?

What does the `@ResponseBody` annotation do?

What does the `@RestController` annotation do?

Describe each of the following annotations briefly:
`@RequestBody`
`@PathVariable`
`@QueryParam`
`@RequestMapping`
`@GetMapping`/`@PostMapping`/etc.

What should Spring controller methods return?

How do you set the status of a response using ResponseEntity?

How do you set the body of a response using ResponseEntity?

Describe each part of the Spring MVC architecture and how they relate to each other:
DispatcherServlet
HandlerMapping
ViewResolver
Controllers

Why don't we use the ViewResolver in our applications?

## Spring Data

What is Spring Data JPA?

What is the JPA? *(note - the JPA is entirely separate from Spring. it is just used by the Spring Data framework.)*

What is an ORM? What problem does it solve?

Describe each of the following JPA annotations:
`@Entity`
`@Table`
`@Column`
`@Id`
`@OneToMany`/`@OneToOne`/`@ManyToMany`/etc.
`@JoinColumn`/`@JoinTable`
`@Transient`

What is a repository in this context?

What do you need to do in your DAO/repository interfaces to have Spring Data write the implementation for you?

What are some methods on the JpaRepository/CrudRepository interfaces?

What is transaction propagation?

What does the `@Transactional` annotation do?

## Spring Test

What does the MockBean annotation do?

What is the SpringBootTest annotation?

What is the MockMvc object?

How do you send a request using MockMvc?

What kinds of things can you "expect" from a response using MockMvc?

What are the two ways you can initialize the MockMvc object?

