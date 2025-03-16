---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [DIContainer](DIContainer.md)
___

instead of using service.AddSingleton you can have custom factory:
 ```cs
 // Using ImplementationType
var descriptorWithType = new ServiceDescriptor(
    typeof(IMyService),
    typeof(MyService),
    ServiceLifetime.Singleton
);

// Using ImplementationInstance
var myServiceInstance = new MyService();
var descriptorWithInstance = new ServiceDescriptor(
    typeof(IMyService),
    myServiceInstance
);

// Using ImplementationFactory
var descriptorWithFactory = new ServiceDescriptor(
    typeof(IMyService),
    provider => new MyService(),
    ServiceLifetime.Transient
);

// Adding descriptors to the service collection
services.Add(descriptorWithType);
services.Add(descriptorWithInstance);
services.Add(descriptorWithFactory);
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
