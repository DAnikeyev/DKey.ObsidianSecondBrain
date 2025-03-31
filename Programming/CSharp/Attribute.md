---
date_added: 2025-02-01
tags:
  - csharp
sr-due: 2025-04-04
sr-interval: 3
sr-ease: 253
---
Up: [Reflection](Reflection.md), [Other CSharp Features](Other%20CSharp%20Features.md)
___
 Attributes add metadata to your program.
- You can apply one or more attributes to entire assemblies, [Module](Module.md), or smaller program elements such as classes and properties.
- Attributes can accept arguments in the same way as methods and properties.
- You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.
- Your program can examine its own metadata or the metadata in other programs by using [Reflection](Reflection.md).

>[!Info]
>The C# keywords `protected` and `internal` have no meaning in Intermediate Language (IL) and are not used in the reflection APIs. The corresponding terms in IL are _Family_ and _Assembly_. To identify an `internal` method using reflection, use the [IsAssembly](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.methodbase.isassembly) property. To identify a `protected internal` method, use the [IsFamilyOrAssembly](https://learn.microsoft.com/en-us/dotnet/api/system.reflection.methodbase.isfamilyorassembly).

## Short name
Attribute `[Obsolete]` is defined by class `[System.ObsoleteAttribute]`. Classes don't have to have names ending with `Attribute`. but if they do, you can omit the `Attribute` suffix when using the attribute.

## Constructor
Attributes can have constructors that take arguments. The arguments are specified in parentheses after the attribute name. If the attribute has a parameterless constructor, you can omit the parentheses.

```csharp
[Obsolete("This method is obsolete. Use Method2 instead.")]
public void Method1() { }
```

calls the constructor `ObsoleteAttribute(string message)`.

>[!Info]
> 
Extenstion method Attribute.IsDefined() can be used to check fast if an attribute is applied to a member.

>[!Info]
> Equals() method is overridden in the Attribute class to compare two attributes by their fields.


### Processing attributes without executing constructor
Might be useful for safety.
Accessible through `CustomAttributeData.GetCustomAttributes` method
 ```csharp
 private static void ShowAttributes(MemberInfo attributeTarget) {
	IList<CustomAttributeData> attributes =
	CustomAttributeData.GetCustomAttributes(attributeTarget);
	Console.WriteLine("Attributes applied to {0}: {1}",
	attributeTarget.Name, (
	attributes.Count == 0 ? "None" : String.Empty));
	
	foreach (CustomAttributeData attribute in attributes) {
		// Вывод типа каждого примененного атрибута
		Type t = attribute.Constructor.DeclaringType;
		Console.WriteLine(" {0}", t.ToString());
		Console.WriteLine(" Constructor called={0}", attribute.Constructor);
		IList<CustomAttributeTypedArgument> posArgs =
		attribute.ConstructorArguments;
		Console.WriteLine(" Positional arguments passed to constructor:" +
		((posArgs.Count == 0) ? " None" : String.Empty));
			foreach (CustomAttributeTypedArgument pa in posArgs) {
				Console.WriteLine(" Type={0}, Value={1}",
				pa.ArgumentType, pa.Value);
		}
	IList<CustomAttributeNamedArgument> namedArgs =
	attribute.NamedArguments;
	Console.WriteLine(" Named arguments set after construction:" +
	((namedArgs.Count == 0) ? " None" : String.Empty));
	foreach(CustomAttributeNamedArgument na in namedArgs) {
	Console.WriteLine(" Name={0}, Type={1}, Value={2}",
	na.MemberInfo.Name, na.TypedValue.ArgumentType,
	na.TypedValue.Value);
	}
	Console.WriteLine();
	}
Console.WriteLine();
}
 ```
`
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
