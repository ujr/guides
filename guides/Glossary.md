
# Glossary

This document collects definitions of common concepts,
terms, abbreviations, and acronyms, that are related
to software programming in general.

The idea is that you can link here from your project documentation,
or copy relevant entries into your project documentation. Within
your project documentation, you probably want to add terms from
your project's application domain.

1. [Abbreviations](#abbreviations)
1. [Methodologies](#methodologies)
1. [Concepts](#concepts)
1. [Dictionary](#dictionary)


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

**OOP** = Object-Oriented Programming. Sometimes the acronyms
**OOA** (Object-Oriented Analysis) and **OOD** (Object-Oriented
Design) are also used.

**ORM** = Object-Relational Mapping, a software layer that
mediates between a relational database and an object-oriented
system by storing and retrieving objects in the database.

**POCO** = Plain Old CLR Object  
**POJO** = Plain Old Java Object, an ordinary object,
without any special attributes nor special inheritance, thus not
following any special conventions besides those imposed by the
runtime (CLR or JVM) itself. Plain Old Objects play nicely with
dependency injection and are a good thing!

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

**UML** = Unified Modeling Language, a graphical language for
sketching and documenting the structure and behavior of software
systems. There are several types of UML diagrams, including
class diagrams (class hierarchies and associations), sequence
diagrams (showing interactions along time), use case diagrams
(a users's possible system interactions), and others.

**UTF-8** = Unicode Transformation Format 8-bit, the (variable
width) character encoding of choice for its many nice properties
(sorts the same as the encoded charcter codes, introduces no
extra null bytes, resynchronization is always possible, and ASCII
is a subset). While at it: UTF-8 is an *encoding* (mapping numbers
to bytes), while Unicode is a *charset* (character set, mapping
characters to numbers); ASCII is both.

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

**12-Factor App:** best practices for developing SaaS (cloud)
applications. Published by Heroku developers around 2012.
See <https://12factor.net>

**Aggregation:** a form of association between objects in OOP
that represents a whole/part relationship, where the parts can
live independently of the whole.
Compare *Composition* and *Association*.

**Architectural pattern:** a structuring scheme for software
systems. Examples include: layers, pipes-and-filters, broker,
model-view-controller, CQRS.

**Architecture:** in the sense of software architecture, is
the high-level design of a software system, in terms of its
components, their relationships, also with the environment,
and the principles that guide development and evolution.

**Association:** a relationship between objects (in OOP) or
between modules (in a general sense). An association has a
cardinality (1:1, 1:N, M:1, M:N). In OOP, *Aggregation* and
*Composition* are specific types of associations.

**Cardinality:** describes how many instances can participate
on each side of an association. A useful notation (among many)
is 1 (exactly one), c (zero or one), m (one or many), and
mc (zero, one, or many). Cardinality also denotes the number
of elements in a set.

**Cloud** computing is a model of providing computing services
on-demand over a network. These services are referred to as
IaaS, PaaS, SaaS (Infrastructure, Platform, Software as a Service)
depending on what layers of a computing stack are included:
the bare infrastructure (virtual machines, storage, network),
also a platform (runtime, database, etc), or also an application
level software (like mail, word processing, CRM, etc).

**Cohesion:** how much the elements of an object (or module)
belong together and interact with each other. High cohesion is
desirable, but *coupling* should be kept low.

**Command:** a behavioral *design pattern* where an object
encapsulates an action, thus making the action recordable,
queueable, loggable, composable, etc.

**Complexity:** what you should keep under control. Some complexity
is inherent to the problem being solved and cannot be avoided. But
you should be constantly looking for complexity that accidentially
creaps in and eliminate it.

**Composition:** the general concept of combining simpler
elements to build a more complicated component. In OOP a type
of association where the owned object is destroyed whenever the
owning object is destroyed. Compare *Aggregation* and *Association*.

**Coupling:** the dependency between objects or modules.
For ease of maintainability, keep coupling low (but go for
high *cohesion* within classes or modules).

**Cross-cutting** means touching many aspects of a system.
Cross-cutting concerns are those concerns that touch most
business concerns of a system. Typical examples include:
logging, caching, security, error handling, persistence,
transactions.

**Daemon** /di:mən/: a process running in the background (no user
interaction) and providing a well-defined *service*, such as web
server. Unix term, mythically short for *disk and execution monitor*,
otherwise typically referred to as a *service*.

**Decorator:** a structural *design pattern*, where an existing
component is wrapped. Differs from the *Adapter* in that a
Decorator modifies the wrapped component's functionality.

**Dependency Injection** (DI): the principle that dependencies
of an object should be "injected" from the outside, not created
or searched by the object itself. In practice, injection means
passing an argument to the constructor or setting a property.
The benefit of dependency injection is to avoid hidden dependencies,
to allow independent testing and mocking.

**Deployment:** the act of putting software into operation
by bringing it into its execution environment, traditionally
installation on a computer.

**Design pattern:** a generic and reusable solution to a commonly
occurring problem in (usually object-oriented) programming.
Examples include: Adapter, Builder, Command, Iterator, Observer,
Visitor. It is generally recommended to use the design pattern
name part of the class name that implements such a pattern.
Beware that inappropriate use of patterns may increase complexity.
Design patterns are usually categorized as creational (e.g. Builder),
structural (e.g. Adapter), and Behavioral (e.g. Command).

**Domain-Driven Design** (DDD): an approach to software design
that closely links the implementation to the concepts of the
application domain. The *domain model* is the set of software
abstractions that describe the application domain.

**Encapsulation** refers to the combination of data with methods
and to the hiding of the data behind the methods, e.g. by restricting
access to fields of an object in OOP.

**Entity:** in DDD an object of the application domain, usually
persisted and with a defined life-cycle. In the context of ORM
it refers to a persistent object.

**Environment:** the context in which an object, a component,
or an entire system is working. *Environment variables* or
just *env vars* are textual name-value pairs in the environment
of a process and a preferred configuration mechanism for containers.

**Facade:** a structural *design pattern* that offers
a simplified interface to a more complex system; this
latter system is not modified at all.

**Factory:** a creational *design pattern* where methods
or entire components are in charge of creating objects.

**Feeping Creaturism:** a word play on **creeping featurism,**
more prosaically known as **feature creep,** the excessive
addition and accumulation of features to a product, often
far beyond creating any real value.

**Heisenbug:** a bug in software that appears to disappear
when being investigated; humorously named after Werner Heisenberg
who stated that the act of observing always changes the system
being observed. Heisenbugs are often caused by uninitialized
variables. A typical example with .NET is that looking at the
values of properties in the debugger may cause state changes
that may affect program behaviour. (This is a good reason why
property getters should not modify state.)

A **heuristic** is a practical approach that is likely to
solve a problem, but not guaranteed to succeed. Well known
from the real world is the trial-and-error heuristic.

**Layer:** a logical separation within an application or system.
Typical application layers are: UI (User Interface), BLL (Business
Logic Layer), and DAL (Data Access Layer). Compare **tier**.

**Tier:** a separate physical deployment target (executable,
service, container) of an application or system. Traditionally,
many **layers** are deployed as a single tier.

**Microservice:** a lightweight and specific service component
in a kind of a service-oriented architecture that communicates
with other specific microservices with the idea that it is easy
to deploy and replace individual microservices (continuous deployment).
Usually implemented as a single process in a *container*.

**Murphy's Law:** everything that can go wrong will go wrong,
so you better adopt defensive design and coding. (The origin
and the link with Murphy is not entirely clear, but that is
of little importance here.)

**Observer:** a behavioral *design pattern* where subject
object maintains a list of observer objects and notifies
the observers of changes to the subject's state.

**Pattern:** see *design pattern*.

**Principal:** an entity that can be (or has been)
authenticated, such as a user, a service, a computer, etc.
Principals can be assigned permissions and are used to
control access to ressources.

**Proxy:** a structural *design pattern* where a proxy
object wraps around the subject object, replicates its
interface, but performes extra operations such as logging,
caching, precondition checking.

**Rationale:** the reasoning behind a decision. While decisions
should always be documented, the rationale is optional (though
useful, but may be kept in a separate section).

**Regex:** short for regular expression, a language that can
build patterns to be compared against texts to find interesting
parts. Supports regular languages, thus arbitrary nested structures
cannot be found. Still a very powerful tool. Available in most
programming libraries and many end-user tools, such as your editor.
Basic syntax is quite uniform across tools, but details vary.

**Registry:** a well-known object that other objects use
to find common objects (such as services). The registry
itself is usually a singleton. Be careful to not subvert
the dependency injection principle by having all sorts of
objects pulling their dependencies out of a registry.
Ideally, there is just one registry, namely the IoC container,
and it is the container's job to inject dependencies.

**Refactoring:** the process of changing the internals of
a software without changing its behavior, the idea being
to improve the internal design towards some design guidelines.

**Repository:** in the context of DDD the layer that
retrieves, stores, and deletes entities (domain objects).
Also refers to the managed folder that contains the codebase,
managed by source control systems such as Git or Fossil.

**Scaling:** adapting a system to handle more (or less)
load (users, requests, clients). **Scaling up** or *vertical*
scaling means to increase the capacity of a single machine,
whereas **scaling out** or *horizontal* scaling means to
add more instances of the same type. Horizontal scaling
requires some form of load balancing and tends to be more
complicated, but can provide fault tolerance and may lower
latency.

**Security** is a large topic and not really covered here.
The first question is: what are the goals of security? And the
usual answer is the *CIA Triad*, which stands for Confidentiality,
Integrity, and Availability. Related subtopics are: authentication,
authorization, accountability, privacy, and many more.

**Second System Effect:** describes the effect that whenever
an elegant system is recreated a second time, it tends to
become over-engineered and bloated. The term first appeared
in Brooks's *Mythical Man-Month* in 1975.

**Separation of Concerns:** a design principle stating
that each component (e.g. a class) of a system should be
concerned with only one responsibility. If, say, a class
addresses two different (business or crosscutting) concerns,
it should be refactored into two classes. Also known as the
Single Responsibility Principle, which is one of the five
principles of SOLID.

**Service:** the context of DDD, a service is where logic of
the business domain is implemented, as far as it is not part
of the entities itself (usually because it relates to several
entity types); services are stateless (apart from caching).

**Silver Bullet:** a simple and effective solution to a problem;
in practice, unfortunately, there is *No Silver Bullet* (Brooks 1986):
no single development in technology (or management) will improve
productivity by an order of magnitude within a decade. However,
some developments such as modern high-level languages have
certainly realized very impressive productivity gains.

**Singleton:** a creational *design pattern*, where a class
may only have one instance, called its singleton. For example,
a *registry* is typically implemented as a singleton.

**Wrapper:** a design pattern where an existing component
is wrapped inside the wrapper component. Wrapper is considered
a general term; *adapter*, *decorator*, and *proxy* are types
of wrappers.


## Dictionary

Many of the technical terms can remain in English when used
in other languages, even if there are equivalent terms. This
may not be the stylistically optimal solution, but certainly
the most practical because it often avoids ambiguity and helps
with Internet searches.

| English | German |
|---|---|
| Artifact       | Artefakt |
| Cohesion       | innerer Zusammenhalt |
| Concern        | Belang |
| Crosscutting   | Querschnitts- |
| Daemon         | Daemon, Dämon, Dienst |
| Deployment     | Softwareverteilung |
| Design pattern | Entwurfsmuster |
| Encapsulation  | Kapselung |
| Interface      | Schnittstelle |
| Pattern        | Muster |
| Proxy          | Stellvertreter |
| Rationale      | Begründung |
| Service        | Dienst |
