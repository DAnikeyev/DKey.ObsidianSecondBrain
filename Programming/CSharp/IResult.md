---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [MinimalApi application](MinimalApi%20application.md)
___
 `IResult` is a newer interface introduced with minimal APIs in ASP.NET Core. It's more focused and doesn't require the MVC infrastructure.
 ```cs
 // In Program.cs with minimal APIs
app.MapGet("/api/users/{id}", (int id) => 
{
    if (id <= 0)
        return Results.BadRequest("Invalid ID");
        
    var user = userRepository.GetById(id);
    
    if (user == null)
        return Results.NotFound();
        
    return Results.Ok(user);
});
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
