---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [IWebHostBuilder](IWebHostBuilder.md)
___
 Used in startup class configure method.
 
```cs
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    // Conditional middleware based on environment
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Error");
        app.UseHsts();
    }

    // Add middleware components in sequence
    app.UseHttpsRedirection();
    app.UseStaticFiles();
    app.UseRouting();
    app.UseAuthentication();
    app.UseAuthorization();
    
    app.UseEndpoints(endpoints =>
    {
        endpoints.MapControllers();
        endpoints.MapRazorPages();
    });
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
