---
date_added: 2025-02-25
tags:
  - csharp
---
Up: [Enumerable](Enumerable.md)
___
```cs
public static System.Collections.Generic.IEnumerable<TResult> GroupBy<TSource,TKey,TElement,TResult>(this System.Collections.Generic.IEnumerable<TSource> source, Func<TSource,TKey> keySelector, Func<TSource,TElement> elementSelector, Func<TKey,System.Collections.Generic.IEnumerable<TElement>,TResult> resultSelector);
```


 ```cs
 using System;
using System.Collections.Generic;
using System.Linq;

public class Employee
{
    public string Name { get; set; }
    public string Department { get; set; }
    public int Age { get; set; }
}

public class Program
{
    public static void Main(string[] args)
    {
        // Sample list of employees.
        List<Employee> employees = new List<Employee>
        {
            new Employee { Name = "Alice", Department = "HR", Age = 30 },
            new Employee { Name = "Bob", Department = "IT", Age = 25 },
            new Employee { Name = "Charlie", Department = "HR", Age = 28 },
            new Employee { Name = "David", Department = "IT", Age = 32 },
            new Employee { Name = "Eva", Department = "Finance", Age = 29 }
        };

        // Example 1: GroupBy using keySelector and elementSelector.
        // - keySelector: employee => employee.Department extracts the Department.
        // - elementSelector: employee => employee.Name transforms each Employee to just their Name.
        var groupByDepartment = employees.GroupBy(
            employee => employee.Department,   // keySelector: determines the group key (Department)
            employee => employee.Name          // elementSelector: transforms each employee to just the Name
        );

        Console.WriteLine("Grouping by Department (showing names only):");
        foreach (var group in groupByDepartment)
        {
            Console.WriteLine("Department: " + group.Key);
            foreach (var employeeName in group)
            {
                Console.WriteLine(" - " + employeeName);
            }
        }
        
        // Example 2: GroupBy using a resultSelector.
        // This overload uses:
        // - keySelector: selects the key (Department).
        // - elementSelector: selects the element to be grouped (here we keep the full Employee object).
        // - resultSelector: transforms each grouping into a custom shape with summary information.
        var groupedResult = employees.GroupBy(
            employee => employee.Department,   // keySelector: selects the department key
            employee => employee,              // elementSelector ▋
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
