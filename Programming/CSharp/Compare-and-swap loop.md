---
date_added: 2025-01-28
tags:
  - csharp
---
Up: [Concurrent collection](Concurrent%20collection.md)
___
Is a lock free method to update collection.

Implementation using `intrinsic` attribute of [[CLR]] to make sure operations inside are atomic
```cs
//Linked list push example

public void Push(T item)
{
	SpinWait spin = default;
	Node node = new (item);
	node._next=  head;

	while (Interlocked.CompareExchange (ref _head, node, node_next != node._next)
	{
		spin.SpinOnce(sleep1Threshold: -1);
		node._next = head;
	}
}
		   
[AtomicPlease]
 public T CompareExchange<t>(ref T location, T value, T comparand)
 {
	 var currentValue = location;
	 if(Equals(currentValue, comparand))
		 location = value;
	 return current Value;
 }
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
