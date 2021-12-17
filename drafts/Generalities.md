
# General Guidelines

This document gives some general guidelines for the
practical software programmer. They are not specific
to any particular programming language or technology.
Guidelines are heuristics to help write good programs;
they are not strict rules. Always use your own judgement.

1. Principles
1. Complexity
1. Codebase
1. Dependencies
1. Configuration
1. Automation
1. Formatting
1. Naming
1. Comments
1. Versioning
1. Testing
1. Documentation
1. Licensing
1. Rationale
1. Bibliography and References
1. Appendix: Pike on Complexity
1. Appendix: Your Project Guidelines

## Principles

Principles are the condensed experience of others; they can be
effective guidelines, but are no replacement for your own
experience. Here are a few:

- KISS (Keep It Simple, Stupid):
  systems work best when they are simple.
- YAGNI (You Ain't Gonna Need It):
  implement things only when you need them
  (because you cannot predict the future).
- DRY (Don't Repeat Yourself):
  avoid repetition of code or information,
  everything should have a single authoritative source.
- Fail early: it will lead you closer to the root cause.

## Complexity

> Controlling complexity is the essence of computer programming.
> —B.W. Kernighan

Therefore:
Aim for **self-documenting code** and strict **separation of concerns**.
Write **highly cohesive** but **loosely coupled** components, and
**build on abstractions** but avoid premature generalization.

Address complexity at all levels:
architecture, solution design, algorithms, files, and code.

On the design level,

- beware of abstraction abundance
- avoid deep class hierarchies
- prefer composition over inheritance

On the algorithmic level, follow these well-known aphorisms:

- Premature optimization is the root of all evil (Donald Knuth)
- When in doubt, use brute force (Ken Thompson)
- Write stupid code that uses smart data (anonymous)
- See Rob Pike's rules in the appendix

On the file level,

- avoid long files (usually less than 500 lines)
- avoid deep directory nesting

On the code level, guidelines largely depend on the language
used and on the company/project cultural background; however,
these are general enough to always apply:

- use care when naming variables and functions (see below),
- avoid long functions (usually less than 25 lines),
- avoid functions with many parameters (usually no more than 4),
- avoid magic constants (except 0 and 1),
- avoid function calls in the condition part of statements
  (use an extra variable with a descriptive name),
- avoid assignment in the condition part of statements,
- assert your assumptions.

## Codebase

The **codebase** is the collection of source artifacts that are
required to build your product (application, component, system,
whatever). The idea is that on any development and build machine,
after a checkout of the codebase the product can be built and
automated tests can be run. Here are some guidelines:

- always keep the codebase in a source control system (e.g. Git)
- keep codebase and product in a one-to-one relation
- include all artifacts needed to build the product: all source
  files, non-code assets, test data, and build tools (except
  those shared among all your products like your compiler)
- see the section about dependencies (libraries)
- always have a README file at root level that answers what
  (this code is) and how (to build it), usually also why it
  is being written, how it is licensed, and how to contribute
- do **not** include configuration in the codebase
- **never** include credentials in the code base
- may include trial code (experiments) but keep in separate
  areas and separate from test code
- prefer flat file structures over deep nesting
- consider having a “commons” area for reusable components
  (you may reuse them in your other projects)
- keep the source control system history as linear as possible
- avoid long-living branches (prefer [OneFlow][OneFlow] over
  [GitFlow][GitFlow] and be pragmatic, [GitHub flow][GitHubFlow]
  works with pull requests)

The top-level of a codebase looks like this (or a subset):

```text
README.md           always have a README, prefer markdown
LICENSE             plain text file but no file extension
.gitignore          files to exclude from source control
.editorconfig       basic formatting rules
src/                source code files
doc/                technical documentation    (1)
lib/                tracked dependencies (3rd party stuff)
test/               test data and protocols    (2)
build/              tools and data needed at build-time only
scripts/            administration and setup scripts
data/               assets that do not fit elsewhere
```

- (1) user documentation may reside outside codebase
- (2) unit test code may be in test/ or in src/

## Dependencies

Either include dependencies (your own and third-party libraries
or packages) into the code base, or declare them explicitly and
have a build process that can resolve them automatically from
some (public) repository (such as [NuGet][NuGet]). Do not rely
on system-wide packages. Use your dependencies in full isolation.

With third party APIs it's best practice to wrap them: this
minimizes your dependency upon them and lets you change the
underlying library with minimal effort.

## Configuration

A codebase has more than one deployment: there are development
machines, test servers, maybe a staging environment, and the
production deployment. The Twelve-Factor App calls them **deploys**
and the **configuration** is what varies between deploys.
Configuration includes, for example, database connection strings,
credentials for external services, port numbers, etc.
Follow these guidelines:

- go for strict separation of config from code
- consider using environment variables for configuration

Note that internal “static” configurations such as app routing
tables or parts of IoC container configuration shall be part
of the codebase as they do not change between deploys.

Environment variables are an easy way to inject configuration
information. Security requirements may prohibit the use of
environment variables for credentials, in which case a specific
credential store could be used (and an environment variable to
reference a location within this store).

## Automation

The benefit of automation is not so much for the efficiency
gainend than for reproducability and avoidance of human error.
Therefore:

- building is one step (a command or a button click)
  and works right after checkout
- running all unit tests is one step

Continuous integration and continuous delivery (CI/CD) is
where you want to go and an automated build is the necessary
prerequisite.

## Formatting

Most programming languages allow much formatting freedom.
Consistent formatting helps with readability and avoids
noise in change sets. Follow these guidelines:

- define rules for formatting
- use UTF-8 but no BOM
- within code, stick to ASCII (occasional exceptions
  for string literrals and comments)
- use CRLF line ends when developing on/for Windows
- provide a *.editorconfig* file to document and enforce formatting

[EditorConfig](https://editorconfig.org) is a standard that
proclaims a *.editorconfig* file that can define some basic
formatting rules and is understood by all major editors.

## Naming

- names say what (intent), not how (implementation)
- avoid abbreviations and acronyms
  (a project may define exceptions)
- do not encode scope (m_foo) nor type (sName);
  your modern IDE can provide this information
- prefer readability over brevity
  (CanScrollVertically, not ScrollableY)
- length of name relates to size of its scope:
  a long name with a small scope is obfuscating,
  `i` is perfectly fine in a tight loop
- avoid identifiers that conflict with keywords
  of common programming languages
- do not use names that differ only by case
  (some languages are not case sensitive)
- avoid generic names such as Element or Node or Item
  (except maybe for a nested private type)
- use design pattern suffixes like ...Adapter, ...Bridge, ...Factory

## Comments

- use comments sparingly, document only the non-obvious
- use English language with proper spelling and grammar
- obsolete or erroneous comments are worse than no comments
- hint: extracting a method or introducing a variable
  often spares a comment

## Versioning

- use **semantic versioning** if your project is a developer-facing component
- use **calendar versioning** if your project is a user-facing application
- always increment the version whenever a build leaves the development team
- consider automatic version increment

Semantic versioning is useful for dependency management because
it clearly states what a version increment means for compatibility.
See <https://semver.org/> about semantic versioning.

For an end-user a calendar (date) based version number is probably
more meaningful and therefore preferred. See <https://calver.org/>
for different schemes of calendar versioning.

## Testing

Automated tests let you fearlessly change your code, thereby
keeping it up to requirements, clean, and maintainable. Without
tests, you stop making changes for fear of breaking something.
Use a coverage tool to see if your tests are sufficient.
Tests are documentation by example.
Tests are always worth the effort.
Here are some guidelines:

- have clean tests with good coverage
- run your tests, and run them frequently
- make tests fast (for if they're slow, you'll not run them)
- maintain tests as the business code evolves
- include test data with the codebase: tests must run successfully
  after a checkout (but try hard to not bloat the codebase)
- keep tests strictly self-contained and independent of each other!
- establish a naming convention for tests

**Unit tests** operate on a single component or function:

- put special care on boundary conditions (empty collections,
  first/last elements, min/max integers, etc.)
- keep tests in separate projects but as part of the codebase
- for each test, follow the 3A pattern: arrange, act, assert
- tests are not trials: they are expected to run successfully!

**Integration tests** operate on two or more components to test
they work together as designed. They may include infrastructure
concerns and take more work for setup. Still the same guidelines
as for unit tests apply.

**End-to-end tests** operate on the user interface level:

- automation needs simulation of user input and may be
  too much effort; alternatively:
- establish a smoke test workflow (test protocol as part
  of the code base)

**Load tests** see if the product can handle the required workload.
As a special case, **stress tests** see if the product recovers
gracefully from extreme (more than the expected or specified)
workloads.

**Regression tests** ensure that a problem will not occur again.
They may be realised at the unit test level or a higher level.
At the very least document them in a test protocol.

**Learning tests** are experiments to check your understanding
of an API, engraving your knowledge into some simple unit tests.
They are also useful to detect incompatible changes in 3rd party
APIs later on (in this sense they are also called *boundary tests*).

- use a naming convention to indicate learning tests as such
- you may keep them close to your unit tests, but don't mix them
- ignore them on automatic execution if they are known to break

Testing is surrounded by a number of **methodologies** including
TDD (write unit test first), BDD (behaviour: given-when-then),
ATDD (acceptance tests first). You often cannot afford strictly
following some methodology, but you should know they exist. Note
that the 3A pattern (arrange-act-assert, aka build-operate-check)
is somewhat equivalent of BDD's given-when-then pattern.

## Cross-cutting Concerns

Functionality that occurs in many programs but cannot be tied to
any single aspect of a program is called a *cross-cutting concern*.
Typical examples include:
logging, tracing, security, error handling, caching, monitoring.

**Logging** is an invaluable diagnostic tool as it provides context
to user error reports. As audit logging it can also be used to gain
insight into a user's behaviour—but beware of ethical considerations
and privacy regulations. Here are some guidelines:

- always have some logging functionality
- if your product is software-as-a-service, log to stdout and/or stderr
- if your product is a self-contained application, use a logging library
  (such as log4net, but do your evaluation)
- library code must not configure logging—this is under application control!
- avoid custom log levels (usually, TRACE, DEBUG, INFO, WARN, ERROR
  should suffice)
- do not log sensitive information (such as credentials or session keys)
- utility methods should not log except at DEBUG level
- when a component logs an ERROR, it should also throw an exception
- beware of performance: message formatting in an inner loop can
  incur a substantial overhead!

**Error handling** guidelines

- error handling is a separate concern
- error handling should not obscure the main logic
- use exceptions instead of returning error codes
- throwing an exception is often more appropriate than returning null

**Security** depends very much on requirements, the type of
software being developed, and the technologies being used.
Some general guidelines apply nevertheless:

- validate all user input
- keep things simple and fail early
- do not log or otherwise disclose sensitive information
- do serious (penetration) testing
- look at security from an architectural point of view:
  define at what layer what access controls apply

## Documentation

- always have a README file at the root level of your codebase
- include developer documentation in the codebase
- use Markdown (*.md) to have it automatically rendered by common
  source control systems
- keep user documentation in the codebase if you can afford keeping
  it in sync with the code
- more than often you cannot, so keep it in a separate wiki system

## Licensing

- always have a LICENSE file at the root level of your codebase
- set copyright year and copyright owner as appropriate
- follow your employer's requirements and guidelines
- do not add a license at the start of each source file
- for maximum reusability, choose a permissive open-source license
  (MIT or BSD or Apache) or release your software into the public
  domain (use The Unlicense).

## Rationale

Guidelines say how, not why. Sometimes they are random choices,
sometimes “by history”, and sometimes there is a real reason.

- Fail Early is a useful guideline. But in a sense, it
  contradicts the Robustness Principle (Postel's Law).
  Robustness is certainly a desirable property of any
  program, but it fosters sloppy input. The dilemma might
  be resolved by seeing that making a program robust requires
  some effort, whereas failing early is a cheap matter of
  discipline. Go for robustness if you can afford it; otherwise
  fail early (raise an error whenever something looks suspicious).

- Whether or not to use the BOM (byte-order-mark) with UTF-8
  is depated. On Windows there is a tendency to use it, while
  in Web projects there is a strong tendency to not use it.
  I chose to recommend against its use because it is invisible
  and serves no real purpose.

- I like and recommend *.editorconfig* because it not only
  configures basic formatting rules, but also documents them
  in a highly visible and readable way.

## Bibliography and References

This bibliography is certainly biased, incomplete, and partially
off-topic. Indeed, it is a personal choice of a few texts I consider
worth reading. Consider assembling your own list for your project.
The list here is ordered by year of first publication.

- Fred Brooks,
  *The Mythical Man Month. Essays on Software Engineering*,
  Addison-Wesley 1975, 1982, 1995. The well-known “Brooks Law”
  that adding people to a late software project makes it later
  is the core of the first essay in the book.
  [Amazon](https://www.amazon.com/dp/0201835959)

- Abelson and Sussman,
  *Structure and Interpretation of Computer Programs*,
  MIT Press 1984, 2nd ed. 1996. Also known as “SICP” it teaches
  fundamental principles of computer programming using the language
  Scheme. Available online at <http://mitpress.mit.edu/sicp>

- Rob Pike, *Notes on Programming in C*, 1989,
  [archived at Lysator](https://www.lysator.liu.se/c/pikestyle.html).
  This is the full paper from which the *Pike on Complexity* appendix
  is an excerpt.

- Eric S. Raymond, *The Cathedral and the Bazaar*, 1999.
  An essay on two different software engineering methods,
  top down (the cathedral) or bottom up (the bazaar), based
  on the surprising success of Linux, which is developed by
  a loose bunch of seemingly uncoordinated individuals from
  around the world.
  [Amazon](https://www.amazon.com/dp/0596001088) and
  [online](http://www.catb.org/esr/writings/cathedral-bazaar/)

- Robert C. Martin,
  *Clean Code. A Handbook of Agile Software Craftsmanship*,
  Pearson 2008.
  A classic about writing readable and maintainable code,
  with a strong focus on object-oriented programming and Java.
  [Amazon](https://www.amazon.com/dp/0132350882)

- Erich Gamma et al.,
  *Design Patterns. Elements of Reusable Object-Oriented Software*,
  Addison-Wesley 1994.
  Also known as the “GoF (Gang of Four) patterns”.
  [Amazon](https://www.amazon.com/dp/0201633612) and
  [Wikipedia](https://en.wikipedia.org/wiki/Design_Patterns).

- Eric Evans,
  *Domain-Driven Design: Tackling Complexitx in the Heart of Software*,
  Addison-Wesley, 2004.

- [Python Logging HOWTO](https://docs.python.org/3/howto/logging.html).
  If unfamiliar with logging, read this for a general appreciation
  of logging; all common logging libraries use similar concepts
  and similar terminology.

- Dave Kerr's collected
  [Hacker Laws](https://github.com/dwmkerr/hacker-laws)
  contains a large number of principles and “laws” related
  to software engineering.

Besides the bibliography above, the following sources have
been consulted for the compilation if this document and
are recommended for follow up:

- EditorConfig at <https://editorconfig.org>
- The Twelve-Factor App at <https://12factor.net>
  (and company internal [presentation](https://github.com/ujr/presentations/tree/master/TwelveFactorApp))
- OneFlow blog article at <https://www.endoflineblog.com/oneflow-a-git-branching-model-and-workflow>
- 3A–Arrange, Act, Assert at <https://xp123.com/articles/3a-arrange-act-assert>
- Apache logging services at <http://logging.apache.org/>
- [Glossary](./Glossary.md) of programming
- [Copyright and Licensing](./CopyrightNotes.md)
- [Markdown Style Guide](./MarkdownStyle.md)
- [Culture](./Culture.md) around programming
- [Resources](./Resrouces.md) for daily work


## Appendix: Pike on Complexity

In an essay on programming in C, Rob Pike stated these rules
on how to cope with complexity:

> Most programs are too complicated – that is, more complex
> than they need to be to solve their problems efficiently.
> Why? Mostly it's because of bad design, but I will skip that
> issue here because it's a big one.  But programs are often
> complicated at the microscopic level, and that is something
> I can address here.
>
> **Rule 1.**  You can't tell where a program is going to spend
> its time.  Bottlenecks occur in surprising places, so don't try
> to second guess and put in a speed hack until you've proven
> that's where the bottleneck is.
>
> **Rule 2.**  Measure.  Don't tune for speed until you've measured,
> and even then don't unless one part of the code overwhelms the rest.
>
> **Rule 3.**  Fancy algorithms are slow when *n* is small, and *n*
> is usually small.  Fancy algorithms have big constants. Until you
> know that *n* is frequently going to be big, don't get fancy.
> (Even if *n* does get big, use Rule 2 first.)  For example, binary
> trees are always faster than splay trees for workaday problems.
>
> **Rule 4.**  Fancy algorithms are buggier than simple ones, and
> they're much harder to implement.  Use simple algorithms as well
> as simple data structures.
>
> The following data structures are a complete list for almost all
> practical programs:
>
> - array
> - linked list
> - hash table
> - binary tree
>
> Of course, you must also be prepared to collect these into compound
> data structures.  For instance, a symbol table might be implemented
> as a hash table containing linked lists of arrays of characters.
>
> **Rule 5.**  Data dominates.  If you've chosen the right data
> structures and organized things well, the algorithms will almost
> always be self­evident.  Data structures, not algorithms, are central
> to programming.  (See Brooks p. 102.)
>
> **Rule 6.**  There is no Rule 6.

## Appendix: Your Project Guidelines

It is useful if a software project has guidelines for development.
It is useful if these guidelines are tuned to the specifics of
the project, but do not neglect the general guidelines of the craft.
Therefore, it should prove useful to build project guidelines in
layers, e.g. like this:

1. Project-specific guidelines (stored in codebase)
2. Language/technology-specific guidelines
   (referenced from project guidelines)
3. General programming guidelines such as this document
   (referenced from project guidelines)

As experience is gained, the guidelines should be updated
to reflect new knowledge and practices. Always update the
guidelines at the appropriate level; this way the more
general guidelines are automatically available to all your
other software projects.

[OneFlow]: http://endoflineblog.com/oneflow-a-git-branching-model-and-workflow
[GitFlow]: http://nvie.com/posts/a-successful-git-branching-model/
[GitHubFlow]: https://guides.github.com/introduction/flow/
[NuGet]: https://www.nuget.org/
