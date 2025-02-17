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
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
