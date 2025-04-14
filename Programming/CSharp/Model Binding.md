---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [Controller in Asp.Net](Controller%20in%20Asp.Net.md)
___
Is a [MiddleWare in WebApi](MiddleWare%20in%20WebApi.md)

Model binding in ASP.NET Core is a feature that automatically maps data from HTTP requests (such as route values, query strings, form data, and JSON payloads) to C# objects or method parameters.

## Binding options

| Attribute/Annotation | Example Snippet                                                                    | Description/Comment                                                                                                    |
| -------------------- | ---------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| [FromQuery]          | public IActionResult Get([FromQuery] int id)                                       | Binds a parameter from the query string (e.g., ?id=123).                                                               |
| [FromRoute]          | public IActionResult Get([FromRoute] int id)                                       | Binds a parameter from the route segment, matching placeholder names defined in routing templates.                     |
| [FromBody]           | public IActionResult Post([FromBody] Model model)                                  | Binds data from the request body (typically JSON), automatically deserializing it to the specified model type.         |
| [FromForm]           | public IActionResult Upload([FromForm] IFormFile file)                             | Binds data submitted via form fields (multipart/form-data), commonly used for file uploads.                            |
| [FromHeader]         | public IActionResult Get([FromHeader] string token)                                | Binds a parameter from a specific HTTP request header.                                                                 |
| [FromServices]       | public IActionResult Get([FromServices] IService svc)                              | Injects a service instance from the dependency injection container into the action method.                             |
| [HttpGet("{id}")]    | [HttpGet("{id}")]\npublic IActionResult Get(int id)                                | Applies a route template on an action; the portion in braces (e.g., {id}) is automatically bound as a route parameter. |
| [Bind]               | public IActionResult Post([Bind("Name,Age")] Person person)                        | Restricts binding to the specified properties of a model, useful for whitelisting or preventing over-posting.          |
| [ModelBinder]        | public IActionResult Get([ModelBinder(BinderType = typeof(MyBinder))] Model model) | Specifies a custom model binder to control how the parameter is bound from the request.                                |
| [BindProperty]       | [BindProperty]\npublic string Name { get; set; }                                   | Commonly used in Razor Pages to automatically bind properties from form data on GET or POST requests.                  |

 ```cs
 using Microsoft.AspNetCore.Mvc;
using System;
using System.Collections.Generic;

namespace MyApp.Controllers
{
    [ApiController]
    [Route("[controller]")]
    public class WeatherForecastController : ControllerBase
    {
        // Simple model binding from route and query string
        // GET /WeatherForecast?temperature=25
        [HttpGet]
        public IActionResult Get([FromQuery] int temperature)
        {
            // The temperature parameter is bound from the query string.
            return Ok($"The temperature is {temperature}°C.");
        }

        // Complex model binding from the request body.
        // POST /WeatherForecast
        [HttpPost]
        public IActionResult Post([FromBody] WeatherForecast forecast)
        {
            if (!ModelState.IsValid)
            {
                return BadRequest(ModelState);
            }
            // Process the forecast data
            return Ok($"Forecast for {forecast.Date.ToShortDateString()} received.");
        }
    }

    // A complex type used for model binding.
    public class WeatherForecast
    {
        public DateTime Date { get; set; }
        public int TemperatureC { get; set; }
        public string Summary { get; set; }
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
