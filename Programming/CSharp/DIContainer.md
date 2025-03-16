---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [Dependency Injection in AspNet](Dependency%20Injection%20in%20AspNet.md)

---

Is defined in Microsoft.Extensions.DependencyInjection

 Contains classes like [IServiceCollection](IServiceCollection.md)

```cs
static ServiceProvider RegisterServices()
{
	var services = new ServiceCollection();
	services.AddSingleton<IGreetingService, GreetingService>();
	services.AddTransient<HomeController>();
	return services.BuildServiceProvider();
}

static void Main()
{
	using (ServiceProvider container = RegisterServices())
	{
		var controller = container.GetRequiredService<HomeController>();
		string result = controller.Hello("Katharina");
		Console.WriteLine(result);
	}
}
```

Here are some popular methods provided by `IServiceCollection` for registering services:

1. **AddSingleton**: This method registers a service with a singleton lifetime. A single instance of the service is created and shared throughout the application's lifetime.
    
    ```csharp
    services.AddSingleton<IMyService, MyService>();
    ```
    
2. **AddScoped**: This method registers a service with a scoped lifetime. A new instance is created per scope. In web applications, a scope is typically created per request.
    
    ```csharp
    services.AddScoped<IMyService, MyService>();
    ```
    
3. **AddTransient**: This method registers a service with a transient lifetime. A new instance is created each time the service is requested.
    
    ```csharp
    services.AddTransient<IMyService, MyService>();
    ```
    
4. **Add**: This method allows you to add a custom `ServiceDescriptor` directly to the collection.
    
    ```csharp
    services.Add(new ServiceDescriptor(typeof(IMyService), typeof(MyService), ServiceLifetime.Singleton));
    ```
    
5. **TryAdd**: These methods are used to add a service only if a service of the same type hasn't already been registered. Variants include `TryAddSingleton`, `TryAddScoped`, and `TryAddTransient`.
    
    ```csharp
    services.TryAddSingleton<IMyService, MyService>();
    ```
    
6. **AddHostedService**: This method is used to register a background service that implements `IHostedService`.
    
    ```csharp
    services.AddHostedService<MyBackgroundService>();
    ```
    
7. **AddHttpClient**: This method is used to register and configure `HttpClient` instances.
    
    ```csharp
    services.AddHttpClient<IMyService, MyService>();
    ```
    
8. **AddOptions**: This method is used to register configuration options.
    
    ```csharp
    services.AddOptions<MyOptions>().Bind(configuration.GetSection("MyOptions"));
    ```
    

These methods provide a flexible way to configure how services are instantiated and managed within an application, supporting various lifetimes and configurations to suit different application needs.


# Getting service

| Method                  | Description                                                                                   | Example Usage                                                                                                                             |
| ----------------------- | --------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `GetService`            | Attempts to retrieve a service of the specified type. Returns `null` if not registered.       | `var myService = serviceProvider.GetService<IMyService>();`                                                                               |
| `GetRequiredService`    | Retrieves a service of the specified type. Throws an exception if not registered.             | `var myService = serviceProvider.GetRequiredService<IMyService>();`                                                                       |
| `CreateScope`           | Creates a new `IServiceScope` for resolving scoped services.                                  | `using (var scope = serviceProvider.CreateScope()) { var scopedService = scope.ServiceProvider.GetRequiredService<IMyScopedService>(); }` |
| `GetServices`           | Retrieves all registered services of the specified type. Returns an empty collection if none. | `var myServices = serviceProvider.GetServices<IMyService>();`                                                                             |
| `GetService<T>`         | Generic version of `GetService`, providing type inference.                                    | `var myService = serviceProvider.GetService<MyService>();`                                                                                |
| `GetRequiredService<T>` | Generic version of `GetRequiredService`, providing type inference.                            | `var requiredService = serviceProvider.GetRequiredService<MyService>();`                                                                  |

## Adding existing instances or factories;
```cs
services.AddSingleton<INumberService>(numberService); // add existing
services.AddTransient<IServiceB>(CreateServiceBFactory);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
