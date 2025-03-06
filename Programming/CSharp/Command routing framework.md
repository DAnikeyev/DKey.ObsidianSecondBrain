---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Using attributes to build extendable application](Using%20attributes%20to%20build%20extendable%20application.md)
___
 ```cs
 using System;
using System.Collections.Generic;
using System.Linq;
using System.Reflection;

// Command attribute
[AttributeUsage(AttributeTargets.Method)]
public class CommandAttribute : Attribute
{
    public string Name { get; }
    
    public CommandAttribute(string name)
    {
        Name = name;
    }
}

// Command handler interface
public interface ICommandHandler
{
}

// Example command handler
public class FileCommandHandler : ICommandHandler
{
    [Command("open")]
    public void OpenFile(string path)
    {
        Console.WriteLine($"Opening file: {path}");
    }
    
    [Command("save")]
    public void SaveFile(string path, bool overwrite = false)
    {
        Console.WriteLine($"Saving file: {path} (Overwrite: {overwrite})");
    }
    
    [Command("delete")]
    public void DeleteFile(string path)
    {
        Console.WriteLine($"Deleting file: {path}");
    }
}

// Example command handler
public class NetworkCommandHandler : ICommandHandler
{
    [Command("connect")]
    public void Connect(string server, int port = 80)
    {
        Console.WriteLine($"Connecting to {server}:{port}");
    }
    
    [Command("disconnect")]
    public void Disconnect()
    {
        Console.WriteLine("Disconnecting from server");
    }
}

// Command router
public class CommandRouter
{
    private Dictionary<string, (MethodInfo Method, object Instance)> _commands = 
        new Dictionary<string, (MethodInfo, object)>(StringComparer.OrdinalIgnoreCase);
    
    public void RegisterHandlers(params ICommandHandler[] handlers)
    {
        foreach (var handler in handlers)
        {
            var type = handler.GetType();
            var methods = type.GetMethods()
                .Where(m => m.GetCustomAttribute<CommandAttribute>() != null);
                
            foreach (var method in methods)
            {
                var attr = method.GetCustomAttribute<CommandAttribute>();
                _commands[attr.Name] = (method, handler);
            }
        }
    }
    
    public bool ExecuteCommand(string commandName, params object[] args)
    {
        if (_commands.TryGetValue(commandName, out var command))
        {
            command.Method.Invoke(command.Instance, args);
            return true;
        }
        
        return false;
    }
    
    public IEnumerable<string> GetAvailableCommands()
    {
        return _commands.Keys;
    }
}

// Usage example
public class Program
{
    public static void Main()
    {
        var router = new CommandRouter();
        
        // Register command handlers
        router.RegisterHandlers(
            new FileCommandHandler(),
            new NetworkCommandHandler()
        );
        
        // Display available commands
        Console.WriteLine("Available commands:");
        foreach (var command in router.GetAvailableCommands())
        {
            Console.WriteLine($"- {command}");
        }
        
        // Execute commands
        Console.WriteLine("\nExecuting commands:");
        router.ExecuteCommand("open", "document.txt");
        router.ExecuteCommand("save", "document.txt", true);
        router.ExecuteCommand("connect", "example.com", 8080);
        router.ExecuteCommand("disconnect");
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
