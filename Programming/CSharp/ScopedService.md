---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [DIContainer](DIContainer.md)
___
In [ASP.NET Core](ASP.NET%20Core.md) Instance created 1 for multiple calls of a single request

 ```cs
 private static void UsingScoped()
{
	//...
	using (ServiceProvider container = RegisterServices())
	{
		using (IServiceScope scope1 = container.CreateScope())
		{
			IServiceA a1 = scope1.ServiceProvider.GetService<IServiceA>();
			a1.A();
			IServiceA a2 = scope1.ServiceProvider.GetService<IServiceA>();
			a2.A();
				IServiceB b1 = scope1.ServiceProvider.GetService<IServiceB>();
			b1.B();
			IServiceC c1 = scope1.ServiceProvider.GetService<IServiceC>();
			c1.C();
			IServiceC c2 = scope1.ServiceProvider.GetService<IServiceC>();
			c2.C();
		}
	Console.WriteLine("end of scope1");
	}
//...
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
