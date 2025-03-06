---
date_added: 2025-03-06
tags:
  - design
---
Up: [Architecture](Architecture.md)
___
 ```cs
 using System;
using System.Collections.Generic;
using System.Linq;
using System.Reflection;

// Custom attribute to mark plugin classes
[AttributeUsage(AttributeTargets.Class)]
public class PluginAttribute : Attribute
{
    public string Name { get; }
    public string Description { get; }
    
    public PluginAttribute(string name, string description = "")
    {
        Name = name;
        Description = description;
    }
}

// Plugin interface
public interface IPlugin
{
    void Execute();
}

// Example plugin implementations
[Plugin("ReportGenerator", "Generates various types of reports")]
public class ReportGeneratorPlugin : IPlugin
{
    public void Execute()
    {
        Console.WriteLine("Generating reports...");
    }
}

[Plugin("DataImporter", "Imports data from external sources")]
public class DataImporterPlugin : IPlugin
{
    public void Execute()
    {
        Console.WriteLine("Importing data...");
    }
}

// Plugin loader
public class PluginLoader
{
    public IEnumerable<IPlugin> LoadPlugins()
    {
        var plugins = new List<IPlugin>();
        
        // Get all types in the current assembly that implement IPlugin and have the PluginAttribute
        // or use Assembly asm = Assembly.Load("PluginLib");
        var pluginTypes = Assembly.GetExecutingAssembly().GetTypes()
            .Where(t => typeof(IPlugin).IsAssignableFrom(t) && !t.IsInterface && !t.IsAbstract)
            .Where(t => t.GetCustomAttribute<PluginAttribute>() != null);
            
        foreach (var type in pluginTypes)
        {
            plugins.Add((IPlugin)Activator.CreateInstance(type));
        }
        
        return plugins;
    }
    
    public void DisplayPluginInfo()
    {
        var pluginTypes = Assembly.GetExecutingAssembly().GetTypes()
            .Where(t => typeof(IPlugin).IsAssignableFrom(t) && !t.IsInterface && !t.IsAbstract)
            .Where(t => t.GetCustomAttribute<PluginAttribute>() != null);
            
        foreach (var type in pluginTypes)
        {
            var attr = type.GetCustomAttribute<PluginAttribute>();
            Console.WriteLine($"Plugin: {attr.Name} - {attr.Description}");
        }
    }
}

// Usage example
public class Program
{
    public static void Main()
    {
        var loader = new PluginLoader();
        
        Console.WriteLine("Available plugins:");
        loader.DisplayPluginInfo();
        
        Console.WriteLine("\nExecuting plugins:");
        foreach (var plugin in loader.LoadPlugins())
        {
            plugin.Execute();
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
