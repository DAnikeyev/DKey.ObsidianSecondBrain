---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [ASP.NET Core](ASP.NET%20Core.md) [Dependency Injection](Dependency%20Injection.md)
___


## Benefits:

- Loose coupling(No direct dependency)
- Easy to test (mocking)
- Easy to maintain(Change implementation without changing the consumer)
- Implementations for different environments
## Defining a Service

To define a service, you first declare a contract for the service. This is done via an interface, which allows you to separate the service implementation from its use. This separation is beneficial, for example, when you want to use a different implementation for unit testing.

### Service Contract

The contract for a sample service is defined in an interface (code file: `WebSampleApp/Services/ISampleService.cs`):

```csharp
public interface ISampleService
{
    IEnumerable<string> GetSampleStrings();
}
```

### Service Implementation


```csharp
public class DefaultSampleService : ISampleService
{
    private List<string> _strings = new List<string> { "one", "two", "three" };
    
    public IEnumerable<string> GetSampleStrings() => _strings;
}
```

## Registering the Service
```cs
public void ConfigureServices(IServiceCollection services)
{
	services.AddTransient<ISampleService, DefaultSampleService>();
	//...
}
```

See [IServiceCollection](IServiceCollection.md) for more.

## Injecting the Service

The built-in dependency injection framework makes use of constructor
injection;
```cs
services.AddTransient<ISampleService, DefaultSampleService>();
services.AddTransient<HomeController>();
// HomeController constructor will use DefaultSampleService if defined like: HomeController(ISampleService service) 
```

Instead of using the Map method, you can also use MapWhen to filter request.



# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
