---
date_added: 2025-03-13
tags:
  - csharp
sr-due: 2025-04-04
sr-interval: 3
sr-ease: 250
---
Up: [ASP.Net](ASP.Net.md)
___
 WebApplication  
• Represents the configured web app instance that is ready to configure middleware and endpoints, and then run the application.  
• Obtained by calling builder.Build() on a [WebApplicationBuilder](WebApplicationBuilder.md) instance.  
• Provides a simplified API for setting up request pipelines, routing, and endpoints, eliminating the need for a traditional Startup class.  
• It also handles common hosting patterns like mapping controllers, minimal APIs, and static files, making it easier for developers to quickly set up and run web applications.

```cs
// Create a new instance of the WebApplicationBuilder class, which is used to configure the application.
var builder = WebApplication.CreateBuilder(args);

// Configure services for dependency injection.
// Add support for controllers and views, which is essential for MVC applications.
builder.Services.AddControllersWithViews();

// Build the WebApplication instance from the configured builder.
var app = builder.Build();

// Configure middleware for the application.

// Check if the application is not running in the development environment.
if (!app.Environment.IsDevelopment())
{
    // Use a centralized exception handling page for production environments.
    // Redirects users to the "/Home/Error" page if an unhandled exception occurs.
    app.UseExceptionHandler("/Home/Error");

    // Enable HTTP Strict Transport Security (HSTS) to enforce the use of HTTPS.
    // This is a security feature that helps protect against man-in-the-middle attacks.
    app.UseHsts();
}

// Redirect HTTP requests to HTTPS to ensure secure communication.
app.UseHttpsRedirection();

// Enable serving of static files (e.g., HTML, CSS, JavaScript, images) from the "wwwroot" folder.
app.UseStaticFiles();

// Add routing middleware to the request pipeline.
// This is necessary for mapping incoming requests to the appropriate endpoints.
app.UseRouting();

// Add authorization middleware to ensure that access to certain resources is restricted based on user roles or claims.
app.UseAuthorization();

// Define a default route for the application using the MVC pattern.
// This route pattern maps URLs to controllers and actions, with an optional "id" parameter.
// If no controller or action is specified in the URL, it defaults to "Home" and "Index", respectively.
app.MapControllerRoute(
    name: "default",
    pattern: "{controller=Home}/{action=Index}/{id?}");

// Start the application and begin listening for incoming HTTP requests.
app.Run();
```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
