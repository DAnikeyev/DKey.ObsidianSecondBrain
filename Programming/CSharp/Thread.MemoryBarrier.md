---
date_added: 2025-03-24
tags:
  - csharp
---
Up: [[Thread]]
___
 Disallow [Compilation process](Compilation%20process.md) to reorder statements if there is a Barrier between them.
```cs
class Foo
{
  int _answer;
  bool _complete;
 
  void A()
  {
    _answer = 123;
    Thread.MemoryBarrier();    // Barrier 1**
    _complete = true;
    Thread.MemoryBarrier();    // Barrier 2**
  }
 
  void B()
  {
    Thread.MemoryBarrier();    // Barrier 3**
    if (_complete)
    {
      Thread.MemoryBarrier();       // Barrier 4**
      Console.WriteLine (_answer);
    }
  }
}
```

>[!Info]
> Without a barrier or [volatile](volatile.md) keyword reordering and caching can lead to 0 being printed.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
