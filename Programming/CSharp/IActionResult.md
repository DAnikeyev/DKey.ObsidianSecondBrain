---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [Controller in Asp.Net](Controller%20in%20Asp.Net.md)
___
 `IActionResult` is the older interface that comes from the MVC pattern in ASP.NET MVC and ASP.NET Core MVC.

```cs
public class HomeController : Controller
{
    public IActionResult Index()
    {
        return View(); // Returns ViewResult
    }

    public IActionResult GetData()
    {
        var data = new { Name = "John", Age = 30 };
        return Json(data); // Returns JsonResult
    }

    public IActionResult NotFound()
    {
        return StatusCode(404); // Returns StatusCodeResult
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
