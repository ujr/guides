<!-- markdownlint-disable MD029 -->

# Fossil Coding Style

Source: <https://fossil-scm.org/home/doc/tip/www/style.wiki>,
minimally edited.

Fossil source code should follow the style guidelines below.

The Fossil source tree includes a few files taken from external sources
(examples: [linenoise](https://github.com/antirez/linenoise) and
[zLib](http://zlib.net/)) and this externally sourced code might not
comply with these style guidelines.

## General points

10. No line of code exceeds 80 characters in length.  
    (Occasional exceptions are made for HTML text on @-lines.)

11. There are no tab characters.

12. Line terminators are `\n` only. Do not use a `\r\n` line terminator.

13. 2-space indentation is used. Remember: No tabs.

14. Comments contain no spelling or grammatical errors. (Abbreviations
    and sentence fragments are acceptable when trying to fit a comment
    on a single line as long as the meaning is clear.)

15. The tone of comments is professional and courteous. Comments contain
    no profanity, obscenity, or innuendo.

16. All C-code conforms to **ANSI C-89.**
    Three well-defined existing exceptions are:

    1. `-Wno-overlength-strings`: The Fossil build system converts
       (some of the) source code comments into strings, which may exceed
       the 509 character limit defined by ANSI. (example: bld/page_index.h)
    2. `-Wno-long-long`: Fossil uses the `long long` integer type,
       which is not strictly ANSI C-89 (defined in C99). The use of
       `long long` resolves many problems with 64-bit arithmetics,
       especially on 32-bit machines. (http_ssl.c, sha3.c, shell.c, util.c)
    3. `alloca()`: By default, sqlite3.c is compiled with the
       -DSQLITE_USE_ALLOCA flag to use the alloca() function. `alloca()`
       is not considered ANSI C, and normally not recommended due to
       portability issues, but performance and/or memory consumption
       improvement may be a stronger argument in favor of its usage.
       (sqlite3.c)

17. All comments and identifiers are in English.

18. The program is single-threaded. Do not use threads. (One exception
    to this is the HTTP server implementation for Windows, which we do
    not know how to implement without the use of threads.)

## C preprocessor macros

20. The purpose of every preprocessor macros is clearly explained
    in a comment associated with its definition.

21. Every preprocessor macro is used at least once.

22. The names of preprocessor macros clearly reflect their use.

23. Assumptions about the relative values of related macros are
    verified by asserts. Example: `assert(READ_LOCK+1==WRITE_LOCK);`

## Function header comments

30. Every function has a header comment describing the purpose
    and use of the function.

31. Function header comment defines the behavior of the function
    in sufficient detail to allow the function to be re-implemented
    from scratch without reference to the original code.

32. Functions that perform dynamic memory allocation (either directly
    or indirectly via subfunctions) say so in their header comments.

## Function bodies

40. The name of a function clearly reflects its purpose.

41. Automatic variables are small, not large objects or arrays.
    Avoid excessive stack usage.

42. The check-list items for functions also apply to major
    subsections within a function.

43. All code subblocks are enclosed in `{...}`.

44. **`assert()` macros are used as follows:**

    - Function preconditions are clearly stated and verified by asserts.
    - Invariants are identified by asserts.

## Class (struct) declarations

50. The purpose and use of every class (a.k.a. structure) is clearly
    defined in the header comment of its declaration.

51. The purpose and use of every class member is clearly defined
    either in the header comment of the class declaration or when
    the member is declared or both.

52. The names of class members clearly reflect their use.

53. Invariants for classes are clearly defined.

## Variables and class instances

60. The purpose and use of every variable is defined by a comment
    at the variable definition.

61. The names of variables clearly reflect their use.

62. Related variables have related names
    (ex: `aSavepoint` and `nSavepoint`).

63. Variables have minimum practical scope.

64. Automatic variables are small, not large objects or arrays.

65. Constants are `const`.

66. Invariants on variables or groups of variables are defined
    and tested by asserts.

67. When a variable that refers to the same value is used within
    multiple scopes, the same name is used in all cases.

68. When variables refer to different values, different names are
    used even when the names are in different scopes.

69. Variable names with wide scope are sufficiently distinctive
    to allow searching for them using grep.
