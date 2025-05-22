---
date_added: 2025-05-22
tags:
  - csharp
---
Up: [CSharp Fundamentals](CSharp%20Fundamentals.md)
___
 A namespace is a domain for type names. Types are typically organized into
hierarchical namespaces, making them easier to find and avoiding conflicts.

>[!Info]
> You can refer to a type with its fully qualified name, which includes all namespaces
from the outermost to the innermost

```cs
namespace Outer
{
	namespace Middle
	{
		namespace Inner
		{
			class Class1 {}
			class Class2 {}
		}
	}
}
```

is equal to having Outer.Middle.Inner namespace.

### File-scoped namespace
Starting from C# 10 you can use
```cs
namespace MyNamespace;
```

## The using Directive
The using directive imports a namespace, allowing you to refer to types without
their fully qualified names.

## The global using Directive

From C# 10, if you prefix a using directive with the global keyword, the directive
will apply to all files in the project or compilation unit:
 ```csharp
global using System;
global using System.Collection.Generic;
 ```

## Implicit global usings

If the ImplicitUsings element is set to true in the project file
System
System.Collections.Generic
System.IO
System.Linq
System.Net.Http
System.Threading
System.Threading.Tasks
Additional namespaces are imported, based on the project SDK (Web, Windows
Forms, WPF, and so on).

## Using static

The using static directive imports a type rather than a namespace. All static
members of the imported type can then be used without qualification

 ```csharp
 using static System.Console;
 WriteLine ("Hello");
 ```

>[!Info] Name hiding
If the same type name appears in both an inner and an outer namespace, the inner
name wins. To refer to the type in the outer namespace, you must qualify its name:

## Extern aliases

If 2 libraries have same namespaces like that:
```cs
namespace Widgets
{
	public class Widget {}
}
```

specifying in csproj file:
```xml
<ItemGroup>
	<Reference Include="Widgets1">
	<Aliases>W1</Aliases>
	</Reference>
	<Reference Include="Widgets2">
	<Aliases>W2</Aliases>
	</Reference>
</ItemGroup>
```

helps resolve ambiguity by calling:
```cs
extern alias W1;
extern alias W2;
W1.Widgets.Widget w1 = new W1.Widgets.Widget();
W2.Widgets.Widget w2 = new W2.Widgets.Widget();
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
