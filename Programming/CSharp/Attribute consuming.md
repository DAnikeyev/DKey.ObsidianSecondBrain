---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [Attribute](Attribute.md)
___
 ```cs
 private static void ReflectOnAttributesUsingEarlyBinding()
{
	Type t = typeof(Winnebago);

	object[] customAtts = t.GetCustomAttributes(false);

	foreach (VehicleDescriptionAttribute v in customAtts)
	Console.WriteLine("-> {0}\n", v.Description);
}
```

Or dynamically:

```cs
{
	Assembly asm = Assembly.Load("AttributedCarLibrary");

	Type vehicleDesc =
asm.GetType("AttributedCarLibrary.VehicleDescriptionAttribute");

	PropertyInfo propDesc = vehicleDesc.GetProperty("Description");

	Туре[] types = asm.GetTypes();

	foreach (Type t in types)
	{
		object[] objs = t.GetCustomAttributes(vehicleDesc, false);


		foreach (object о in objs)
		{
			Console.WriteLine("-> {0}: {l}\n", t.Name, propDesc.GetValue (o, null));
		}
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
