---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Using attributes to build extendable application](Using%20attributes%20to%20build%20extendable%20application.md) [Dependency Injection](Dependency%20Injection.md)
___
```cs
using System;
using System.Reflection;

// Attribute to mark properties for injection
[AttributeUsage(AttributeTargets.Property)]
public class InjectAttribute : Attribute { }

// Service interfaces and implementations
public interface ILogger
{
    void Log(string message);
}

public class ConsoleLogger : ILogger
{
    public void Log(string message)
    {
        Console.WriteLine($"LOG: {message}");
    }
}

public interface IDataService
{
    string GetData();
}

public class SqlDataService : IDataService
{
    public string GetData()
    {
        return "Data from SQL Server";
    }
}

// Simple dependency injection container
public class DependencyContainer
{
    private Dictionary<Type, object> _services = new Dictionary<Type, object>();
    
    public void Register<TInterface, TImplementation>() where TImplementation : TInterface, new()
    {
        _services[typeof(TInterface)] = new TImplementation();
    }
    
    public T Resolve<T>()
    {
        if (_services.TryGetValue(typeof(T), out var service))
        {
            return (T)service;
        }
        throw new InvalidOperationException($"Service of type {typeof(T).Name} not registered");
    }
    
    public void InjectDependencies(object instance)
    {
        var type = instance.GetType();
        var properties = type.GetProperties()
            .Where(p => p.GetCustomAttribute<InjectAttribute>() != null);
            
        foreach (var property in properties)
        {
            var serviceType = property.PropertyType;
            if (_services.TryGetValue(serviceType, out var service))
            {
                property.SetValue(instance, service);
            }
            else
            {
                throw new InvalidOperationException($"Cannot inject dependency of type {serviceType.Name}");
            }
        }
    }
}

// Example class with dependencies
public class UserService
{
    [Inject]
    public ILogger Logger { get; set; }
    
    [Inject]
    public IDataService DataService { get; set; }
    
    public void ProcessUser()
    {
        Logger.Log("Processing user...");
        var data = DataService.GetData();
        Logger.Log($"Retrieved data: {data}");
    }
}

// Usage example
public class Program
{
    public static void Main()
    {
        var container = new DependencyContainer();
        
        // Register services
        container.Register<ILogger, ConsoleLogger>();
        container.Register<IDataService, SqlDataService>();
        
        // Create and inject dependencies
        var userService = new UserService();
        container.InjectDependencies(userService);
        
        // Use the service
        userService.ProcessUser();
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
