
# Resources for your daily work

## Quick answers

- StackExchange at <https://stackexchange.com/>,
  a large Q&A site on many topics
- StackOverflow at <https://stackoverflow.com/>
  is the StackExchange for programming Q&A
- Code Project at <https://www.codeproject.com/>,
  a community site with articles and source code
- GitHub at <https://github.com>, not just to host your repos,
  but also a huge source of practical code
- Rosetta Code at <http://rosettacode.org>,
  a site with implementations of the same task
  in many languages
- [Can I use?](https://caniuse.com) at <https://caniuse.com>
  provides Browser compatibility tables
- Popular interview questions by technology at <https://github.com/FAQGURU>
- The [comp.lang.c FAQ](http://c-faq.com/) at <http://c-faq.com/>

## Architecture & Design

- Best practices for SaaS (web apps) at <https://12factor.net>
  (The Twelve-Factor App)
- Collection of architectural patterns at <https://patterns.arc42.org>
- Microservice patterns at <https://microservices.io>
- Best practices for RESTful APIs at <https://restfulapi.net/>
- Web: MPA, SPA, RWD, PWA
- *Patterns of Enterprise Application Architecture* (PEAA) (Fowler, 2003)
  ([author's page](https://martinfowler.com/books/eaa.html))
  ([Amazon](https://www.amazon.com/dp/0321127420))
- *Domain-Driven Design* (DDD) (Evans, 2003)
  ([web page](https://www.domainlanguage.com/))
  ([Amazon](https://www.amazon.com/dp/0321125215))
- Many blogs address these topics, including [blog.ploeh.dk](https://blog.ploeh.dk)
- [Clean Architecture Cheat Sheet](https://www.bbv.ch/ueber-uns/publikationen/clean-architecture-prinzipien-und-methoden-im-ueberblick/)
  (bbv Software Services, 2015)
- [Unified Modeling Language](https://en.wikipedia.org/wiki/Unified_Modeling_Language)
  (UML); [Violet](https://horstmann.com/violet/) is an easy UML editor
- The [arc42](https://arc42.org) software architecture
  documentation template

## Coding

- *Design Patterns* (Gamma et al., 1994) (dt. Entwurfsmuster)
  ([Amazon](https://www.amazon.com/dp/0201633612))
- <https://clean-code-developer.com> •
  “more professionalisim in software development”
- <https://clean-code-developer.de> • das selbe auf Deutsch
- <https://developer.mozilla.org> • the Mozilla Web Dev Docs, comprehensive
- <https://xlinux.nist.gov/dads/> • the NIST *Dictionary of
  Algorithms and Data Structures* (Paul E. Black, ed., since at least 1998)
- Establish code conventions and provide project templates
- Style and Coding guides (e.g.
  [PEP-8](https://www.python.org/dev/peps/pep-0008/) for Python,
  [Framework Design Guideines](https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/)
  for .NET)
- [Clean Code Cheat Sheet](https://www.bbv.ch/ueber-uns/publikationen/clean-code-prinzipien-und-umsetzung/)
  (bbv Software Services, 2015)
- [Convention over Configuration](https://en.wikipedia.org/wiki/Convention_over_configuration)
- Know [regular expressions](https://en.wikipedia.org/wiki/Regular_expression);
  beware that the details and capabilities differ between tools and libraries:
  [.NET](https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference),
  [POSIX](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap09.html),
  [Perl](https://perldoc.perl.org/perlrequick),
  [AWK](https://www.gnu.org/software/gawk/manual/html_node/Regexp.html),
  [JavaScript](https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions),
  or try online at [regexr.com](https://regexr.com)
- Use [UTF-8 text encoding](https://utf8everywhere.org/) when you have a choice
- Use [EditorConfig.org](https://editorconfig.org) for
  basic formatting conventions

## Testing

- [Software testing](https://en.wikipedia.org/wiki/Software_testing)
  on Wikipedia
- Level of testing: unit, integration, system, acceptance
- Further types: smoke, performance, load, UI, penetration, end-to-end
- Testing party: alpha (software producer), beta (freindly end users)
- Methodologies: TDD (unit tests first), BDD (given-when-then),
  ATDD (acceptance test driven development)
- Patterns and best practices
  (3A, UI vs “headless”, generating test data, etc.)
- [Clean TDD/ATDD Cheat Sheet](https://www.bbv.ch/ueber-uns/publikationen/clean-tdd-und-atdd-zusammengefasst/)
  (bbv Software Services, 2015)
- Tools (like [xUnit.net](https://xunit.net) for .NET, ...)

## Documentation

- TODO
- Concepts (README, project wiki, printed/printable docs, ...)
- Tools and frameworks (arc42.org, ...)
- Software Bill of Materials (SBOM): SPDX at <https://spdx.dev> is a standard
  format for an SBOM (there are others); a good introduction (in German) is at
  <https://www.csoonline.com/de/a/amp/was-ist-eine-software-bill-of-materials,3674040>

## Security

- The OWASP Foundation at <https://owasp.org>
- SAML, OAuth, ... TODO
- Check your web site's security with <https://observatory.mozilla.org>
- Details of TLS explained at <https://tls13.ulfheim.net>

## UI/UX

- <https://material.io> – Google's Material Design (since 2014)

## Licensing

The resources here are for open source licensing.
For proprietary licensing consult your legal department.
See [Copyright and Licensing](./CopyrightNotes.md) article.

- <https://choosealicense.com> • find your open source license
- <https://tldrlegal.com> • explanation of popular licenses
- <https://opensource.org/licenses> • licenses approved by the OSI
- <https://unlicense.org> • to dedicate your software to the public domain
- <https://creativecommons.org> • licenses for sharing non-code works
- <https://www.gnu.org/licenses/licenses.html> • the GNU licenses

## DevOps

DevOps is the combination of development and operation.
The idea is to provide a continuous flow of customer value.
It requires complete automation of build and deployment:
Build, Test, Package, Release, Deploy, Configure, Monitor.

- Versioning concepts: [semver.org](https://semver.org)
  and [calver.org](https://calver.org)
- Software configuration management:
  [Git](https://git-scm.com),
  [Fossil](https://fossil-scm.org)
- Git's staging area and its ability to commit parts of files
  will help with “semantic” commits for a readable history
- Branching schemes:
  [OneFlow](https://www.endoflineblog.com/oneflow-a-git-branching-model-and-workflow),
  [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/),
  see also [Trunk Based Development](https://trunkbaseddevelopment.com)
- Learn to use Git's staging area and its capability to commit
  only parts of a file
- Cloud: [GitHub](https://github.com),
  [Azure DevOps](https://dev.azure.com),
  [GitLab](https://about.gitlab.com)
- Continuous Integration (CI): fully automated build, including
  automated tests; can be as simple as a well-written
  [Makefile](https://makefiletutorial.com/), or using an
  on-premise build server like [Jenkins](https://www.jenkins.io/),
  or run on cloud-based services like
  [GitHub Actions](https://github.com/features/actions); see also at
  [Wikipedia](https://en.wikipedia.org/wiki/Continuous_integration)
- Continuous Delivery (CD): extends CI by also including automated
  delivery to a test environment, maybe even a production environment.
- Continuous Deployment (CD): the same as continuous delivery, but
  implies even more “continuousness” and automation to the point
  where every change (that does not cause a failed test) is put to
  production; the concept of a “release” no longer applies.
- More common DevOps tools: Ansible, Puppet, Chef, ...

## Methods

- Waterfall (linear development in phases)
- Agile: Scrum, XP, Kanban, ... (development in iterations)
  ([Agile Manifesto](http://agilemanifesto.org/))
- Others: Big Bang, Pair Programming, Code Reviews (Pull Requests)
- Open Source: see [opensource.guide](https://opensource.guide) and
  read [The Cathedral & the Bazaar](http://www.catb.org/esr/writings/cathedral-bazaar/)
  ([Amazon](https://www.amazon.com/dp/0596001088))

## Knowledge

- The iSAQB Glossary of Software Architecture Terminology
  is naturally more architecture focused but still contains
  many software development relevant entries.
  <https://leanpub.com/isaqbglossary/read>
- The Jargon File at <http://www.catb.org/jargon/>
  (and while there also *The Cathedral & the Bazaar*)
- *The Mythical Man Month. Essays on Software Engineering*
  (Fred Brooks, 1975, 1982, 1995)
- [Book of Modern Frontend Tooling](https://tooling.github.io/book-of-modern-frontend-tooling/)
  is unfortunately no longer maintained
- Berufe der ICT: branchenübliche Berufsbilder, zusammengestellt
  vom Branchenverband swissICT auf <https://www.berufe-der-ict.ch>

## Certifications

Beware that there are usually commercial interests behind
a certification. Consequently, there is a plenitude of
certifications on offer, mostly from big software companies.
Here is a very small and mostly random selection.

- <https://www.isaqb.org> training and certification for software architects
- <https://www.lpi.org> The Linux Professional Institute
- <https://scrum.org> offers Scrum certifications
- <https://www.istqb.org> certifications for software testers
- <https://swisstestingboard.org> the Swiss branch of ISTQB
- Microsoft, AWS, etc.
