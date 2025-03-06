---
date_added: 2025-02-02
tags:
  - csharp
---
Up: [Reflection](Reflection.md)
___
 Represents type declarations: class types, interface types, array types, value types, enumeration types, type parameters, generic type definitions, and open or closed constructed generic types.

Contains info about types including [[Assembly]] or other [Reflection](Reflection.md) information.

To get Type, you can use typeof() operator or GetType() method. typeof is used when you don't want to create an object, and GetType is used when is unknown at compile time.

```csharp) 
### Properties

- **Name**: Gets the name of the type
- **Namespace**: Gets the namespace of the type
- **FullName**: Gets the fully qualified name of the type
- **Assembly**: Gets the assembly in which the type is defined
- **BaseType**: Gets the type from which the current type directly inherits
- **IsAbstract**, **IsClass**, **IsEnum**, **IsInterface**, **IsValueType**: Type classification properties
- **IsGenericType**, **IsGenericTypeDefinition**: Properties for working with generic types

### Methods

- **GetConstructors()**: Gets the constructors of the type
- **GetMethods()**: Gets the methods of the type
- **GetProperties()**: Gets the properties of the type
- **GetFields()**: Gets the fields of the type
- **GetEvents()**: Gets the events of the type
- **GetInterfaces()**: Gets the interfaces implemented by the type
- **GetCustomAttributes()**: Gets the custom attributes applied to the type
- **IsAssignableFrom()**: Determines if an instance of a specified type can be assigned to a variable of the current type
- **IsInstanceOfType()**: Determines if the specified object is an instance of the current Type
- **IsSubclassOf()**: Determines if the current type derives from a specified type
- **MakeGenericType()**: Substitutes the specified type arguments for the type parameters of the current generic type definition

 ```csharp
 using System;
using System.Reflection;

class Example
{
    static void Main()
    {
        Type t = typeof(String);

        MethodInfo substr = t.GetMethod("Substring", 
            new Type[] { typeof(int), typeof(int) });

        Object result = 
            substr.Invoke("Hello, World!", new Object[] { 7, 5 });
        Console.WriteLine("{0} returned \"{1}\".", substr, result);
    }
}

/* This code example produces the following output:

System.String Substring(Int32, Int32) returned "World".
 */
 ```

## Complex example: Simple DI container:

```cs
using System;
using System.Collections.Generic;
using System.Reflection;

// Interfaces
public interface IService { void Execute(); }
public interface ILogger { void Log(string message); }

// Implementations
public class ServiceA : IService
{
    private readonly ILogger _logger;
    
    public ServiceA(ILogger logger)
    {
        _logger = logger;
    }
    
    public void Execute()
    {
        _logger.Log("ServiceA is executing");
    }
}

public class ConsoleLogger : ILogger
{
    public void Log(string message)
    {
        Console.WriteLine($"[LOG] {message}");
    }
}

// Simple DI Container
public class Container
{
    private readonly Dictionary<Type, Type> _registrations = new Dictionary<Type, Type>();
    
    public void Register<TInterface, TImplementation>() where TImplementation : TInterface
    {
        _registrations[typeof(TInterface)] = typeof(TImplementation);
    }
    
    public T Resolve<T>()
    {
        return (T)Resolve(typeof(T));
    }
    
    private object Resolve(Type type)
    {
        if (_registrations.TryGetValue(type, out Type implementationType))
        {
            // Get the first constructor
            ConstructorInfo constructor = implementationType.GetConstructors()[0];
            
            // Resolve constructor parameters recursively
            ParameterInfo[] parameters = constructor.GetParameters();
            object[] parameterInstances = new object[parameters.Length];
            
            for (int i = 0; i < parameters.Length; i++)
            {
                parameterInstances[i] = Resolve(parameters[i].ParameterType);
            }
            
            // Create instance
            return constructor.Invoke(parameterInstances);
        }
        
        throw new InvalidOperationException($"Type {type.Name} is not registered");
    }
}

class Program
{
    static void Main()
    {
        // Set up the container
        var container = new Container();
        container.Register<ILogger, ConsoleLogger>();
        container.Register<IService, ServiceA>();
        
        // Resolve and use service
        IService service = container.Resolve<IService>();
        service.Execute();  // Output: [LOG] ServiceA is executing
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
