---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [Code contracts](Code%20contracts.md)
___
 Provides methods for condition checks
```cs
public static class Contract {

// Методы с предусловиями: [Conditional("CONTRACTS_FULL")]
public static void Requires(Boolean condition);
public static void EndContractBlock();

// Предусловия: Always
public static void Requires<TException>(
Boolean condition) where TException : Exception;

// Методы с постусловиями: [Conditional("CONTRACTS_FULL")]
public static void Ensures(Boolean condition);
public static void EnsuresOnThrow<TException>(Boolean condition)
where TException : Exception;

// Специальные методы с постусловиями: Always
public static T Result<T>();
public static T OldValue<T>(T value);
public static T ValueAtReturn<T>(out T value);

// Инвариантные методы объекта: [Conditional("CONTRACTS_FULL")]
public static void Invariant(Boolean condition);

// Квантификаторные методы: Always
public static Boolean Exists<T>(
IEnumerable<T> collection, Predicate<T> predicate);
public static Boolean Exists(
Int32 fromInclusive, Int32 toExclusive, Predicate<Int32> predicate);
public static Boolean ForAll<T>(
IEnumerable<T> collection, Predicate<T> predicate);
public static Boolean ForAll(
Int32 fromInclusive, Int32 toExclusive,
Predicate<Int32> predicate);

// Вспомогательные методы:
// [Conditional("CONTRACTS_FULL")] или [Conditional("DEBUG")]
public static void Assert(Boolean condition);
public static void Assume(Boolean condition);
// Инфраструктурное событие: обычно в коде это событие не используется
public static event EventHandler<ContractFailedEventArgs> ContractFailed;
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
