---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [System.Numerics](System.Numerics.md)
___

Allows faster operations by combining elements (for example 4 floats in 1 vector) for opearations.
```cs
using System;
using System.Numerics;

class Program
{
    static void Main()
    {
        // Define two arrays of floats
        float[] array1 = { 1.0f, 2.0f, 3.0f, 4.0f };
        float[] array2 = { 5.0f, 6.0f, 7.0f, 8.0f };
        float[] result = new float[array1.Length];

        // Ensure the arrays are of the same length
        if (array1.Length != array2.Length)
        {
            throw new ArgumentException("Arrays must be of the same length.");
        }

        // Determine the number of elements that can be processed in parallel
        int vectorSize = Vector<float>.Count;

        // Process the arrays in chunks of vectorSize
        for (int i = 0; i < array1.Length; i += vectorSize)
        {
            // Load elements into vectors
            var v1 = new Vector<float>(array1, i);
            var v2 = new Vector<float>(array2, i);

            // Perform vectorized addition
            var vResult = v1 + v2;

            // Store the result back into the result array
            vResult.CopyTo(result, i);
        }

        // Display the result
        Console.WriteLine("Result of vector addition:");
        foreach (var value in result)
        {
            Console.WriteLine(value);
        }
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
