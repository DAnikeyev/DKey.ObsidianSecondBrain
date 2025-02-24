---
date_added: 2025-01-31
tags:
  - csharp
---
Up: [CSharp Statement](CSharp%20Statement.md)
___

You use the `yield` statement in an [Iteration statement](Iteration%20statement.md) to provide the next value or signal the end of an iteration. The `yield` statement has the two following forms `return x` and `break`:

yield turns method into a state machine.

```cs
Console.WriteLine(string.Join(" ", TakeWhilePositive(new int[] {2, 3, 4, 5, -1, 3, 4})));
// Output: 2 3 4 5

Console.WriteLine(string.Join(" ", TakeWhilePositive(new int[] {9, 8, 7})));
// Output: 9 8 7

IEnumerable<int> TakeWhilePositive(IEnumerable<int> numbers)
{
    foreach (int n in numbers)
    {
        if (n > 0)
        {
            yield return n;
        }
        else
        {
            yield break;
        }
    }
}
```

## async
`yield return await ` can be used for returning [IAsyncEnumerable](IAsyncEnumerable.md)

```cs
await foreach (int n in GenerateNumbersAsync(5))
{
    Console.Write(n);
    Console.Write(" ");
}
// Output: 0 2 4 6 8

async IAsyncEnumerable<int> GenerateNumbersAsync(int count)
{
    for (int i = 0; i < count; i++)
    {
        yield return await ProduceNumberAsync(i);
    }
}

async Task<int> ProduceNumberAsync(int seed)
{
    await Task.Delay(1000);
    return 2 * seed;
}
```

# Custom Iteration

Implementing GetEnumerator() allows to iterate over the fields:
```cs
public static void Example()
{
    var point = new Point(1, 2, 3);
    foreach (int coordinate in point)
    {
        Console.Write(coordinate);
        Console.Write(" ");
    }
    // Output: 1 2 3
}

public readonly record struct Point(int X, int Y, int Z)
{
    public IEnumerator<int> GetEnumerator()
    {
        yield return X;
        yield return Y;
        yield return Z;
    }
}
```

>[!Info] yield can't be used in:
> - methods with [in](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/method-parameters#in-parameter-modifier), [ref](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/ref), or [out](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/method-parameters#out-parameter-modifier) parameters.
> - [lambda expressions](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/lambda-expressions) and [anonymous methods](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/delegate-operator).
> - [unsafe blocks](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/unsafe). Before C# 13, `yield` was invalid in any method with an `unsafe` block. Beginning with C# 13, you can use `yield` in methods with `unsafe` blocks, but not in the `unsafe` block.
> - `yield return` and `yield break` can not be used in [catch](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/exception-handling-statements) and [finally](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/exception-handling-statements) blocks, or in [try](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/exception-handling-statements) blocks with a corresponding `catch` block. The `yield return` and `yield break` statements can be used in a `try` block with no `catch` blocks, only a `finally` block.

## Usage
The call of an iterator doesn't execute it immediately, as the following example shows:
```cs
var numbers = ProduceEvenNumbers(5);
Console.WriteLine("Caller: about to iterate.");
foreach (int i in numbers)
{
    Console.WriteLine($"Caller: {i}");
}

IEnumerable<int> ProduceEvenNumbers(int upto)
{
    Console.WriteLine("Iterator: start.");
    for (int i = 0; i <= upto; i += 2)
    {
        Console.WriteLine($"Iterator: about to yield {i}");
        yield return i;
        Console.WriteLine($"Iterator: yielded {i}");
    }
    Console.WriteLine("Iterator: end.");
}
// Output:
// Caller: about to iterate.
// Iterator: start.
// Iterator: about to yield 0
// Caller: 0
// Iterator: yielded 0
// Iterator: about to yield 2
// Caller: 2
// Iterator: yielded 2
// Iterator: about to yield 4
// Caller: 4
// Iterator: yielded 4
// Iterator: end.
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
