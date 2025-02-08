---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [Application configuration](Application%20configuration.md)
___
 Is a way to define applcation settings.
# Example:

```cs
public class MyAppSettings
{
    public string Setting1 { get; set; }
    public string Setting2 { get; set; }
}
```

```json
{ "MyAppSettings":
	{
	 "Setting1": "Value1",
	 "Setting2": "Value2"
	}
}
```

## Mapping:

 ```csharp
 using System;
using Microsoft.Extensions.Configuration;

class Program
{
    static void Main(string[] args)
    {
        // Build configuration
        var configuration = new ConfigurationBuilder()
            .SetBasePath(AppContext.BaseDirectory)
            .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
            .Build();

        // Bind configuration to the class
        var myAppSettings = new MyAppSettings();
        configuration.GetSection("MyAppSettings").Bind(myAppSettings);

        // Use the configuration
        Console.WriteLine($"Setting1: {myAppSettings.Setting1}");
        Console.WriteLine($"Setting2: {myAppSettings.Setting2}");
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
