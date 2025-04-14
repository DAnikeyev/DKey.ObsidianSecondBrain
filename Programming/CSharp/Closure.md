---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Delegate](Delegate.md)
___
 A closure is a feature in C# (and many other languages) where a lambda expression or anonymous method "closes over" variables defined in its surrounding scope. In simpler terms, even after the method that created these variables has finished executing, the lambda or anonymous method can continue to access and modify these captured variables.

works for [Lambda Expressions](Lambda%20Expressions.md), [Delegate](Delegate.md) and [yield](yield.md) return methods or in any cases when method captures a variable from outer scope.

>[!Important]
>Local variables are captured by reference, not by value. This means that if the variable is modified after the closure is created, the closure will see the updated value.
> 
## Examples

```cs

    public class Example7
    {
        public static void Run()
        {
            Action action = CreateAction();
            action(); // prints: counter=1
            action(); // prints: counter=2
            action(); // prints: counter=3
            action(); // prints: counter=4
            action(); // prints: counter=5
        }

        private static Action CreateAction()
        {
            int counter = 0; // this variable is captured by the delegate below
            return delegate
            {
                counter++;
                Console.WriteLine("counter={0}", counter);
            };
        }
    }
```

 ```csharp
         // Additionally, closures are used in iterators by capturing state between yield returns.
        private static System.Collections.Generic.IEnumerable<int> GenerateNumbers()
        {
            int number = 0;
            while (number < 3)
            {
                yield return number;
                // The state (number) is captured and maintained across iterations.
                number++;
            }
        }

        // This could be called like:
        // foreach(var n in GenerateNumbers()) { Console.WriteLine($"Yielded: {n}"); }
 ```
for yield see [**Compiler-Generated State Machine:**](Deferred%20Execution%20in%20LINQ.md#**Compiler-Generated%20State%20Machine%20**)
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
