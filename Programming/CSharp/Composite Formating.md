---
date_added: 2025-01-26
tags:
  - csharp
---
Up: [String Formating](String%20Formating.md)
___
 ```cs
 string.Format("Name = {0}, hours = {1:hh}", "Fred", DateTime.Now);
```

```cs
string[] names = { "Adam", "Bridgette", "Carla", "Daniel",
                   "Ebenezer", "Francine", "George" };
decimal[] hours = { 40, 6.667m, 40.39m, 82,
                    40.333m, 80, 16.75m };

Console.WriteLine("{0,-20} {1,5}\n", "Name", "Hours");

for (int counter = 0; counter < names.Length; counter++)
    Console.WriteLine("{0,-20} {1,5:N1}", names[counter], hours[counter]);

// The example displays the following output:
//      Name                 Hours
//      
//      Adam                  40.0
//      Bridgette              6.7
//      Carla                 40.4
//      Daniel                82.0
//      Ebenezer              40.3
//      Francine              80.0
//      George                16.8
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
