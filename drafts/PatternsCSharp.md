# Common Patterns in C\#

## Tester-Doer

```C#
var builder = ...
if (builder.CanBuild()) builder.Build();
```

## Try-Parse

As exhibited by .NET primitve types `int`, `double`, etc.
Works equally well for custom types.

```C#
int Parse(string text) {...}  // throw if bad syntax
bool TryParse(string text, out int value) {...} // false if bad syntax
```

## Exception Builder

```C#
private FormatException SyntaxError(int lineNumber, string message) {...}

if (unexpected input)
    throw SyntaxError(CurrentLine, $"Unexpected input: {CurrentToken}");
```

This pattern is **much** preferred over `void SyntaxError(...)` because
it makes control flow visible from the caller.

## Thread-safe Singleton

```C#
public sealed class Singleton                    // prevent derivation
{
   private static volatile Singleton _instance;  // avoid optimizations
   private static readonly object SyncRoot = new Object();

   private Singleton() {}                        // private constructor

   public static Singleton Instance
   {
      get 
      {
         if (_instance is null)        // performance optimization
         {
            lock (SyncRoot)            // mutual exclusion
            {
               if (_instance is null)  // create only once (singleton)
               {
                   _instance = new Singleton();
               }
            }
         }
         return _instance;
      }
   }
}

```

This double-check approach solves thread concurrency problems
while avoiding the locking overhead in each access to the
`Instance` property method.

See also: <https://msdn.microsoft.com/en-us/library/ff650316.aspx>

## Dispose Pattern

- release unmanaged resources (like open files) deterministically
- beware that `Dispose` may be called more than once;
  all but the first call should be no-ops
- in addition to the `Dispose()` method, the dispose pattern mandates
  a `Dispose(bool)` overload for any non-sealed class
- see <https://learn.microsoft.com/dotnet/standard/garbage-collection/implementing-dispose>

## Exception Guidelines

- throw if a method cannot do what it is designed to do
- use exceptions to report errors but not for control flow
- do not use exceptions for code that routinely fails:
  use the Tester-Doer or the Try-Parse pattern instead
- consider the Exception Builder pattern
- throw the most specific exception that is appropriate
- use the exceptions from the `System` namespace (but avoid
  throwing `System.Exception` as it is unsepcific)
- create custom exceptions for a new error type that can
  be handled programmatically
- do not change exception types between versions (you break client code)
- catch (and wrap) only specific exceptions (to avoid hiding errors)
- to re-throw an exception, just say `throw;`
  (**not** `throw ex;` as this would loose the stack trace)
- exception messages: meaningful for a developer, proper English,
  avoid `!` and `?` signs, do not disclose sensitive information

## Common exception types

- `ArgumentNullException` — an argument is null that must not be;
  include parameter name (use `nameof`)
- `ArgumentOutOfRangeException` — an argument is out of range;
  include parameter name (use `nameof`), argument value, and allowed range
- `ArgumentException` — invalid argument but none of the above;
  include parameter name (use `nameof`)
- `InvalidOperationException` — object is in an inappropriate state
  for the operation
- `NotImplementedException` — functionality is not yet implemented
  (but should be)
- `NotSupportedException` — functionality is not implemented
  (and *never will* be)

## Custom Exception

- **Avoid** deep exception hierarchies
- Do **not** derive from `ApplicationException` (contrary to old recommendation)
- **Do** end exception class name with “Exception”
- **Do** provide at least the constructors shown in the code sample below

```C#
public class MyException : Exception
{
    public MyException() {}

    public MyException(string message)
        : base(message) {}

    public MyException(string message, Exception? inner)
        : base(message, inner) {}
}
```
