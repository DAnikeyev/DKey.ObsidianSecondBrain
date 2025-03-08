---
date_added: 2025-02-17
tags:
  - csharp
---
Up: [AppDomain](AppDomain.md)
___
 Enables access to objects across application domain boundaries in applications that support remoting.

## Creating object in another domain
```cs
using System;
using System.Reflection;

public class CreateInstanceWorker : MarshalByRefObject
{
    public void PrintDomain()
    {
        Console.WriteLine("Object is executing in AppDomain \"{0}\"",
            AppDomain.CurrentDomain.FriendlyName);
    }
}

class CreateInstanceAndUnwrapSourceSnippet
{
    public static void Main()
    {
        // Create an ordinary instance in the current AppDomain
        CreateInstanceWorker localWorker = new CreateInstanceWorker();
        localWorker.PrintDomain();

        // Create a new application domain, create an instance
        // of Worker in the application domain, and execute code
        // there.
        AppDomain ad = AppDomain.CreateDomain("New domain");
        CreateInstanceWorker remoteWorker = (CreateInstanceWorker) ad.CreateInstanceAndUnwrap(
            typeof(CreateInstanceWorker).Assembly.FullName,
            "Worker");
        remoteWorker.PrintDomain();
    }
}

/* This code produces output similar to the following:

Object is executing in AppDomain "source.exe"
Object is executing in AppDomain "New domain"
 */
```


## Making object available by Uri

```cs
using System;
using System.Runtime.Remoting;

public class SetObjectUriForMarshalTest  {

    class TestClass : MarshalByRefObject {
    }

    public static void Main()  {

        TestClass obj = new TestClass();

        RemotingServices.SetObjectUriForMarshal(obj, "testUri");
        RemotingServices.Marshal(obj);

        Console.WriteLine(RemotingServices.GetObjectUri(obj));
    }
}
```

## Core Mechanism of MarshalByRefObject

When objects derived from `MarshalByRefObject` are accessed across [Application domain](Application%20domain.md) boundaries, .NET's remoting infrastructure creates a proxy-based communication channel. Here's what happens step by step:

1. **Proxy Generation**: The CLR generates a transparent proxy in the calling AppDomain
2. **Message Formatting**: Method calls are converted to messages
3. **Channel Transportation**: Messages are transported across AppDomain boundaries
4. **Real Object Invocation**: The real object receives and processes the call
5. **Response Marshaling**: Results are marshaled back to the calling AppDomain

**What happens:**

- `CreateInstanceAndUnwrap` instructs the remote AppDomain to:
    1. Load the assembly that contains `RemoteCalculator`
    2. Create an instance of `RemoteCalculator` in the remote AppDomain's memory space
    3. The actual object lives ONLY in the CalculatorDomain (memory address A1B2C3D4)
    4. A proxy object is created in the DefaultDomain (memory address E5F6G7H8)
    5. The proxy is returned to the caller in the DefaultDomain

**Memory allocations:**

- In CalculatorDomain: A real `RemoteCalculator` object with its `_lastResult` field
- In DefaultDomain: A transparent proxy object implementing the same interface

**What happens when `calculator.Add(10, 20)` is called:**

1. The call is intercepted by the proxy in DefaultDomain
2. The proxy creates a **message** containing:
    - Method identifier (Add)
    - Parameter values (10, 20)
3. The message is passed to the remoting infrastructure
4. The remoting channel forwards the message to the CalculatorDomain
5. In CalculatorDomain, the message is deserialized
6. The real `Add` method is invoked on the real object
7. `_lastResult` is updated to 30 in the real object in CalculatorDomain
8. The return value (30) is serialized into a message
9. The message is sent back to DefaultDomain
10. The proxy deserializes the result and returns it to the caller

**Memory allocations during call:**

- Parameters (10, 20) are copied/marshaled across the AppDomain boundary
- Return value (30) is copied/marshaled back


### How Parameters Are Serialized

When you call a method on a `MarshalByRefObject`-derived object across AppDomain boundaries:

1. **Message Formation**: The parameters are packaged into an `IMethodCallMessage` object
    
2. **Serialization Process**: Each parameter is processed according to these rules:

| Parameter Type                   | Handling Mechanism                                    |
| -------------------------------- | ----------------------------------------------------- |
| Value Types (int, double, etc.)  | Directly copied by value                              |
| String                           | Special handling (immutable, efficiently transferred) |
| MarshalByRefObject               | A proxy is created (passed by reference)              |
| `[Serializable]` Objects         | Fully serialized using formatter (binary copy)        |
| Non-Serializable Reference Types | **Exception thrown**                                  |
### Serialization Requirements

For parameters to successfully cross AppDomain boundaries, they must meet one of these criteria:

1. Be a primitive type or value type
2. Be a string
3. Inherit from `MarshalByRefObject`
4. Be marked with the `[Serializable]` attribute
5. Implement the `ISerializable` interface for custom serialization
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
