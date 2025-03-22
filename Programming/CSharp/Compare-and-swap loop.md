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
//Push example
using System;
using System.Threading;
using System.Threading.Tasks;

// A simple node for the linked list.
public class Node
{
    public int Value;
    public Node Next;

    public Node(int value)
    {
        Value = value;
        Next = null;
    }
}

// A lock-free concurrent linked list implementation.
public class ConcurrentLinkedList
{
    private volatile Node head;

    public ConcurrentLinkedList()
    {
        head = null;
    }

    // Adds a new node with the given value at the end of the list using a CAS loop.
    public void Add(int value)
    {
        Node newNode = new Node(value);
        // Create a SpinWait instance for yielding the thread between unsuccessful CAS attempts.
        SpinWait spin = new SpinWait();

        while (true)
        {
            // If the list is empty, try to atomically set the head.
            if (head == null)
            {
                if (Interlocked.CompareExchange(ref head, newNode, null) == null)
                {
                    return; // Successfully added as the first node.
                }
                // If unsuccessful, yield and retry.
                spin.SpinOnce();
            }
            else
            {
                // Traverse the list to locate the last node.
                Node tail = head;
                while (true)
                {
                    Node next = tail.Next;
                    if (next == null)
                    {
                        // Attempt to attach newNode to the end of the list.
                        if (Interlocked.CompareExchange(ref tail.Next, newNode, null) == null)
                        {
                            return; // Successfully added newNode.
                        }
                        // If CAS failed, yield briefly and retry attaching at this position.
                        spin.SpinOnce();
                    }
                    else
                    {
                        tail = next;
                        // Optionally reset the spin counter as we progress.
                        spin.Reset();
                    }
                }
            }
        }
    }

    // Utility method to print the list.
    public void PrintList()
    {
        Node current = head;
        while (current != null)
        {
            Console.Write(current.Value + " -> ");
            current = current.Next;
        }
        Console.WriteLine("null");
    }
}

public class Program
{
    public static void Main()
    {
        ConcurrentLinkedList list = new ConcurrentLinkedList();
        
        // Use TPL's Parallel.For to simulate multiple threads concurrently adding nodes.
        Parallel.For(0, 100, i =>
        {
            list.Add(i);
        });

        // Print the final list.
        list.PrintList();
    }
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
