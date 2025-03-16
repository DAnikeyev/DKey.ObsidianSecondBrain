---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [ASP.Net](ASP.Net.md)
___
 Controllers in ASP.NET Core are a fundamental part of the Model-View-Controller [MVC](MVC.md)architectural pattern. 
 - They are classes that typically inherit from ControllerBase (or Controller if you need view support). Use `[ApiController]` attribute for proper API routing.
- Controllers define action methods that are invoked based on routing configuration. Each action corresponds to a specific endpoint in your web application.
- Routing attributes (such as [Route] and [HttpGet]/[HttpPost]) are typically used to map URLs to the correct action methods.
- Controllers allow for the separation of concerns by keeping the request handling and business logic separate from other aspects of the application (such as data access and view rendering).
- They support features like model binding, validation, and action filters that help manage cross-cutting concerns like logging and exception handling.

## Example
```cs
using Microsoft.AspNetCore.Mvc;

namespace MyWebApi.Controllers
{
    [ApiController]
    [Route("[controller]")]
    public class HomeController : ControllerBase
    {
        // GET /home
        [HttpGet]
        public IActionResult Get() 
        {
            return Ok("Hello from HomeController!");
        }
        
        // GET /home/greet/{name}
        [HttpGet("greet/{name}")]
        public IActionResult Greet(string name)
        {
            return Ok($"Hello, {name}!");
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
