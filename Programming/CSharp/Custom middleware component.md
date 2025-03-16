---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [Middleware component](Middleware%20component.md)
___
 ```csharp
public class HeaderMiddleware
{
    private readonly RequestDelegate _next;

    public HeaderMiddleware(RequestDelegate next) =>
        _next = next;

    public Task Invoke(HttpContext httpContext)
    {
        httpContext.Response.Headers.Add("sampleheader", new[] { "addheadermiddleware" });
        return _next(httpContext);
    }
}
```

To make it easy to configure the middleware type, the extension method `UseHeaderMiddleware` extends the interface `IApplicationBuilder` where the method `UseMiddleware` is called:

```csharp
public static class HeaderMiddlewareExtensions
{
    public static IApplicationBuilder UseHeaderMiddleware(this IApplicationBuilder builder) =>
        builder.UseMiddleware<HeaderMiddleware>();
}
```

Now it’s the job of the `Startup` class and the `Configure` method to configure all the middleware types. The extension methods are already prepared for invocation (code file `WebSampleApp/Startup.cs`):

```csharp
public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
{
    //...
    app.UseHeaderMiddleware();
}
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
