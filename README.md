C# Design Principle - SOLID

# The reason behind most unsuccessful applications

Developers start building applications with good and tidy designs using their knowledge and experience. But over time, applications might develop bugs. The application design must be altered for every change request or new feature request. After some time we might need to put in a lot of effort, even for simple tasks and it might require full working knowledge of the entire system. But we can't blame change or new feature requests. They are part of software development. We can't stop them or refuse them either. So who is the culprit here? Obviously it is the design of the application.

# Problem: 
The following are the design flaws that cause damage in software, mostly.

1. Putting more stress on classes by assigning more responsibilities to them. (A lot of functionality not related to a class.)

2. Forcing the classes to depend on each other. If classes are dependent on each other (in other words tightly coupled), then a change in one will affect the other.

3. Spreading duplicate code in the system/application.

# Solution:

1. Choosing the correct architecture (in other words MVC, 3-tier, Layered, MVP, MVVP and so on).

2. Following Design Principles.

3. Choosing correct Design Patterns to build the software based on its specifications.

# SOLID stands for

S - Single Responsible Principle (SRP).

O - Open Closed Principle (OSP).

L - Liskov Substitute Principle (LSP).

I - Interface Segregation Principle (ISP).

D - Dependency Inversion Principle (DIP).

Michael Feathers introduced the SOLID acronym in the year 2000. SOLID is a design principle that plays a very important role during Object-Oriented design. Software development becomes easy, reusable, flexible, and maintainable using these design principles.

Robert C Martin has promoted SOLID Principles and now it’s very famous. It has changed the development approach and dominated in software development industries.

# Benefits of SOLID

1. It makes software design more understandable, flexible, and maintainable

2. Best suitable principle can be used as per project requirement

3. Loosely coupled

4. Parallel Development

5. Testability

6. Code becomes smaller and cleaner

7. Maintainability – Large Systems or Growing systems become complicated and difficult to maintain. This Principle helps us to create a maintainable system. A maintainable system is very important in industries.

# Single Responsible Principle (SRP)

A class should have ONE and ONLY ONE reason to change

![image](https://github.com/psangrama/Solid-Design-Principle/assets/113549457/e1b586c2-482a-4dbe-8c09-6e8191487f89)

EmployeeService has no relationship with email. This is a bad design.

Where the right design to have separate classes for both EmployeeService and EmailService, as they carries single responsibility as their name suggests.

# Open/Closed Principle(OCP)

Class should be open for extension and closed for modification.

1. Open for extension – means we need to create a base class and that class will be available for extension. This class should have common functionality.

2. Close for Modification – Instead of changing the base class, we will extend the base class and add/modify type-specific coding in the derived class.

![image](https://github.com/psangrama/Solid-Design-Principle/assets/113549457/2864519c-70e8-4285-9789-0b6576af2559)

#Liskov Substitute Principle (LSP)

Subtypes must be substitutable for their base class.

We should not be using inheritance only just to avoid few lines of code in the child class. While inheritance, we always has to ensure child class should replace parent class.

Here in this example, PermanentEmployee is the base class and ContractEmployee is the child class i.e. there is a Parent-Child relationship. So, we can store the child class object in the Parent Reference variable i.e. PermanentEmployee employee = new ContractEmployee(); and when we call the GetLeaves i.e. employee.GetColor(), then we are getting the leaves of ContractEmployee which is not right.

![image](https://github.com/psangrama/Solid-Design-Principle/assets/113549457/535af826-7749-4157-bfb9-f6fd0d5c6a4e)

# Interface Segregation Principle (ISP)

The dependency of one class to another one should depend on the smallest possible interface. - Clients should not be forced to implement interfaces they don't use Instead of one fat interface many smaller interfaces are preferred based on groups of methods, each one serving one sub module.

Here in the example below, we can groom dog but can't groom tiger. But has to have a dummy implementation for the compiler to be happy. Rather the good implementation is to segregate the interface into multiple interfaces like Animal and PetAnimal, so dog can implement PetAnimal and Tiger can implement Animal.

![image](https://github.com/psangrama/Solid-Design-Principle/assets/113549457/2dd7870e-0695-4a5e-9abf-bb9503748319)


# Dependency Inversion Principle:

The principle of dependency inversion refers to the decoupling of software modules. This way, instead of high-level modules depending on low-level modules, both will depend on abstractions.

Other words, depend upon abstractions(interfaces) not upon concrete classes. Secondly, an abstraction must not depend upon details, but the details must depend upon abstractions.

![image](https://github.com/psangrama/Solid-Design-Principle/assets/113549457/fcdea506-ade0-4e28-8b42-6fb6c7847a82)

Other design principles to keep in mind while designing any software application:

# Inversion of Control (IoC):

The main objective of Inversion of Control (IoC) in C# is to remove the dependencies (remove tight coupling) between the objects of an application which makes the application more decoupled and maintainable.

The IoC Design Principle suggests the inversion of various types of controls in object-oriented design to achieve loose coupling between the application classes. Here, control means any extra responsibilities a class has other than its main or fundamental responsibility. For example, control over the flow of an application, control over the dependent object creation, etc.

We can’t accomplish loosely coupled classes by just utilizing IoC in C#. Along with IoC we additionally need to utilize DIP, DI, and IoC containers to achieve loose coupling.

Dependency Injection Design Pattern:

The Dependency Injection (DI) Design Pattern is a software design pattern that allows us to develop loosely coupled code by inverting the creation of dependent objects. Dependency Injection is a great way to reduce the tight coupling between software components. DI also enables us to better manage future changes and other complexity in our software.

The IoC Container is a great framework to create dependencies and inject them automatically whenever required throughout the application outside the class, so we don’t have to put additional time and effort into it. It automatically creates the necessary objects based on the request and also automatically injects them whenever required during runtime. DI Container helps us to manage dependencies within the application in a straightforward and simple way.

There are different IoC Containers available for .NET such as Unity, Ninject, StructureMap, Autofac, etc.

Dependency Injection can be achieved using

1. Property Injection

2. Method Injection

3. Constructor Injection
