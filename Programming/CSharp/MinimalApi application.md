---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [WebApplication (ASP)](WebApplication%20(ASP).md)
___

Uses 
app.MapGet, app.MapPost, app.MapPut and app.MapDelete for [[WebApi Routing]].

Here’s an overview of their key features and benefits:

1. Minimal Boilerplate:  
    You can build an API with just a single file (typically Program.cs), using top-level statements to define the entire application. This reduces the ceremony and boilerplate code required by more traditional approaches.
    
2. Simplified Endpoint Definitions:  
    Minimal APIs allow you to define HTTP endpoints directly using methods like MapGet, MapPost, MapPut, and MapDelete. These methods take a URL pattern and a delegate (e.g., a lambda function) that handles the request, enabling you to quickly set up routes for your API.
    
3. Parameter Binding:  
    The framework automatically binds route parameters, query strings, and even request bodies to the parameters of your endpoint methods. This simplifies the process of getting data from the HTTP request.
    
4. Improved Performance:  
    Because of the reduced abstraction and overhead, minimal APIs can provide faster response times and lower resource consumption, which is especially useful for microservices and small APIs.
    
5. Integrated Middleware and Dependency Injection:  
    Despite their simplicity, minimal APIs still support middleware, dependency injection, and other ASP.NET Core features. This means you can add services (like logging, configuration, and database contexts) and middleware (for authentication, error handling, etc.) as needed.
### For example
```cs
var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

// Define a simple endpoint using routing.
// The route pattern "/" maps to the lambda function that returns a greeting.
app.MapGet("/", () => "Hello, routing and endpoints!");

// Define an endpoint that includes a route parameter.
// The "{name}" segment in the URL is captured and passed as a parameter to the lambda.
app.MapGet("/greet/{name}", (string name) => $"Hello, {name}!");

// Start the application.
app.Run();
```

## Parsing HttpRequest
```cs
  
// Example method using HttpRequest directly  
app.MapPost("/process-request", async (HttpRequest request, IGameRepository repository) =>  
{  
    try  
    {  
        // Access request headers  
        var userAgent = request.Headers["User-Agent"].ToString();  
  
        // Read the request body manually if needed  
        GameDto? gameDto = await request.ReadFromJsonAsync<GameDto>();  
  
        if (gameDto == null)  
        {            return Results.BadRequest("Invalid game data");  
        }  
        // Process the data  
        var game = new Game(gameDto.Name, gameDto.Score, gameDto.Comment);  
        await repository.AddAsync(game);  
  
        // Return response with custom headers  
        var response = Results.Created($"/games/{game.Id}", game);  
  
        // You can also log request information  
        Console.WriteLine($"Request processed from: {userAgent}");  
  
        return response;  
    }    catch (Exception ex)  
    {        return Results.Problem($"Error processing request: {ex.Message}");  
    }});
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
