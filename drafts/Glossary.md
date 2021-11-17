
# Glossary

This document collects definitions of common concepts,
terms, abbreviations, and acronyms, that are related
to software programming in general.

The idea is that you can link here from your project documentation,
or copy relevant entries into your project documentation. Within
your project documentation, you probably want to add terms from
your project's application domain.

## Abbreviations

Software programming abounds with abbreviations and acronyms.
Here is an alphabetical list of general abbreviations; those
relating to specific technologies have not been included.

By the way, abbreviations (lat. *brevis* = short) are shortened
representations of one or several words in a general sense.
There are several types of abbreviations, including contractions
created by omitting syllables (e.g. nil for lat. *nihil*) and
acronyms consisting of the initial parts of a longer word or
several words (e.g. BIOS for *Basic Input/Output System*
or Radar for *radio detection and ranging*
or GNU for *GNU's Not Unix* with its jocular recursion).
There is some dispute whether or not an acronym has to be
pronouncable as a word, though this depends on the language.
In English, for example, GIF (Graphics Interchange Format) is
nicely pronouncable, but PNG (Portable Network Graphics) is not.

Software programming and computer science in general abound
with acronyms to a point where people start making fun of it
and talk of *yet another TLA* (Three-Letter-Acronym).

**API** = Application Programming Interface, the interface
exposed by an application for programmers, and therefore
an interface between programs. The API is directed towards
the human programmer, whereas the ABI (Application Binary
Interface) is about how compiled code interfaces an application.

**CI/CD** = Continuous Integration / Continuous Deployment,
the idea to deliver an application to the end users very
frequently by fully automating the integration (build) and
the deployment in the customer's production environment.

**CLI** = Command Line Interface, once the only way to interact
with a system, now again popular at least for developer tools.

**CQS** = Command/Query Separation, a principle stating that
a method should either be a *command* that changes something
or a *query* that returns something (but without changing
anything). On a larger scale also known as **CQRS** for
Command/Query Responsibility Separation, where the same
principle is applied to objects, components, or subsystems.

**DDD** = Domain Driven Design, after the 2003 book of the same
name by Eric Evans. A high-level software design approach that
attempts to build software by representing the concepts and terms
of the domain experts.

**DI** = Dependency Injection, a mechanism for separating construction
from use; implemented as IoC containers.

**DSL** = Domain-specific Language, either a small scripting language
or an API in the main development language that approaches the language
of a domain expert.

**FIXME** = a comment in code to indicate a place that still
needs work (the idea is that such places are easy to find with
your IDE's search). `/* FIXME this case is not yet handled */`

**GoF** = Gang of Four, after the four authors of the influential
book *Design Patterns. Elements of Reusable Object-Oriented Software*.
Used in statements like *this is one of the GoF patterns*.

**IDE** = Integrated Development Environment, always includes
a text editor, but also integrates additional development
tools like a debugger, a project manager, etc. Well-known
examples include: Visual Studio, Eclipse, XCode.

**iff** = if and only if, necessary and sufficient (either
both statements are true or both are false).

**IoC** = Inversion of Control, (a) the idea of callbacks
as in frameworks (framework calls application code) and
opposed to libraries (application code calls library);
(b) as IoC Conatainer a component that facilitates **DI**
by providing a type registry, dependency resolution, and
lifetime control (like singleton or transient).

**MVP** = Minimum Viable Product, provides just enough features
to be usable by early adopters who then provide feedback to drive
further development.

**POCO** = Plain Old CLR Object  
**POJO** = Plain Old Java Object, an ordinary object,
without any special attributes nor special inheritance, thus not
following any special conventions besides those imposed by the
runtime (CLR or JVM) itself. Plain Old Objects are a good thing!

**REST** = Representational State Transfer, a widely accepted
architectural style for creating Web APIs where, roughly speaking,
a client interacts with a server by applying the HTTP verbs
(GET, POST, PUT, DELETE) to server resources (URLs) that
represent some state (like a file on the server).

**SDK** = Software Development Kit, a set of tools, libraries,
templates, and documentation to build applications for some
platform.

**SOLID** = an acronym for five common design principles
in (mostly object-oriented) programming:

- Single Responsibility Principle
  (each class should have a single responsibility)
- Open-Closed Principle
  (be open for extension, but closed for modification)
- Liskov Substitution Principle (a derived class can always
  be substituted for a base class without any other modification)
- Interface Segregation Principle
  (prefer many specific interfaces over one general-purpose interface)
- Dependency Inversion Principle
  (depend on abstractions, not on implementations)

**TDD** = Test Driven Development: write tests and business code
together, tests being just slightly ahead. Keep the system working
(all tests succeed) at all times, even during large refactorings.

**TL;DR** = Too Long; Didn't Read. Used (a) to introduce a short
summary of a lengthy text, and (b) to indicate that you did not read
such a text.

**TODO** = To Do, a comment in code that something needs review;
e.g. `/* TODO dirty hack */`. See also **FIXME**; in your project
you probably want to use only one or the other.

**UI/UX** = User Interface / User Experience, where the former
refers more to how an interface is presented to and operated by
a user, and the latter is, well, about the total experience of
interacting with a user interface.

**XP** = Extreme Programming, a software development methodology.

## Methodologies

Once the basic technological apsects of programming were
sufficiently developed, more and more people shifted their
focus on methodological aspects of development. Today we
have a plethora of development methodologies to choose from,
to mix, or to ignore. Here are just a few.

**Agile** software development encompasses a number of practices
including adaptive planning, early and iterative delivery,
cross-functional and self-organizing teams, usually in direct
contact with the end users or customers. Other than the older
waterfall model, agile practices accept that requirements
and circumstances constantly change.

**Extreme Programming** is a methodology for agile software
development. Comprises a number of principles and practices,
such as pair programming, code review, short iterations,
refactoring, coding standards, acceptance tests, and many more.
(Kent Beck, *Extreme Programming Explained*, 1999)

**Kaizen** is the continuous monitoring for and application of
small improvements by all members of an organization. If something
is found to be broken, it is immediately fixed, usually by small
simple measures. From Japanese lean manufacturing.

**Kanban,** the singal card scheduling system from lean manufacturing
adapted for software development: in essence, have a central billboard
with some columns (e.g. to do, doing, done) and sticky notes that
represent tasks that progress through the columns. The idea is to have
only few active tasks and visualize.

**Scrum,** a framework for developing software (and other complex
products), based on time-boxed work in *sprints* of typically two
weeks by a cross-functional and self-organizing team. Works well
with XP. For large organizations with many teams, the concept has
been variously extended, resulting in SAFe (Scaled Agile Framework)
and Large-Scale Scrum (LeSS), among others.

**Waterfall,** the sequential execution of plan-design-build-test-deploy.
The problem is, that by the time the planning of an entire system
is done, the entire system according to plan may be obsolete.

## Concepts

**Architectural pattern,** a structuring schema for software.
Examples: layers, pipes-and-filters, model-view-controller,
broker, CQRS.

**Composition,** the general concept of combining simpler
elements to build a more complicated component. ......... (examples)

**Dependency Injection** (DI) is the principle that dependencies
of an object should be "injected" from the outside, not created
or searched by the object itself. In practice, injection means
passing an argument to the constructor or setting a property.
The benefit of dependency injection is to avoid hidden dependencies,
to allow independent testing and mocking.

**Deployment** is the act of putting software into operation
by bringing it into its execution environment, traditionally
installation on a computer.

**Design pattern,** a generic and reusable solution to a commonly
occurring problem in (usually object-oriented) programming.
Examples include: Adapter, Builder, Command, Iterator, Observer,
Visitor. It is generally recommended to use the design pattern
name part of the class name that implements such a pattern.
Beware that inappropriate use of patterns may increase complexity.

**Feeping Creaturism,** a word play on **creeping featurism,**
more prosaically known as **feature creep,** the excessive
addition and accumulation of features to a product, often
far beyond creating any real value.

**Second System Effect,** describes the effect that whenever
an elegant system is recreated a second time, it tends to
become over-engineered and bloated. The term first appeared
in Brooks's *Mythical Man-Month* in 1975.

## Dictionarly

| English | German |
|---|---|
| Deployment | Softwareverteilung |
| Design pattern | Entwurfsmuster |

