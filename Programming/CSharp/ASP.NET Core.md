---
date_added: 2025-03-13
tags:
  - csharp
  - web
---
Up: [Web Development](Web%20Development.md) [ASP.Net](ASP.Net.md)
___

## References
 1. Examples: https://github.com/DAnikeyev/DKey.WebApiExamples


 ASP.NET Core is a cross-platform, high-performance, open-source framework for building modern, cloud-based, and internet-connected applications. Here’s an overview of its key aspects:

• Cross-platform:  
ASP.NET Core runs on Windows, macOS, and Linux. This flexibility helps developers build applications that can be deployed and run on different operating systems, accommodating various environments and cloud providers.

• High performance and modularity:  
The framework is designed for high performance and scalability. It embraces a modular architecture where developers can include only the components needed for their application, reducing overhead and improving efficiency.

• Unified programming model:  
ASP.NET Core supports web APIs, web applications, mobile backends, real-time applications, and more. It combines MVC (Model-View-Controller) and web API functionalities into a single framework, making it easier to create dynamic web applications and services.

• Dependency injection and middleware:  
Built-in dependency injection enhances code testability and modularity. Middleware components form a pipeline to handle HTTP requests and responses, allowing developers to plug in custom logic such as authentication, logging, or error handling.

• Open-source and community-driven:  
The framework is open source, which means the community contributes to its continuous improvement, ensuring that it keeps pace with modern development practices and evolving needs. Documentation and a rich ecosystem of libraries, extensions, and tooling further boost productivity.

## Example
```cs
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.Extensions.Hosting;

namespace MyAspNetCoreApp
{
    public class Startup
    {
        // Configure services adds services to the container.
        public void ConfigureServices(IServiceCollection services)
        {
            // Adds services required for using MVC.
            services.AddControllersWithViews();
        }

        // Configure sets up the HTTP request pipeline.
        public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
        {
            if (env.IsDevelopment())
            {
                app.UseDeveloperExceptionPage();
            }
            else
            {
                // The default HSTS value is 30 days.
                app.UseExceptionHandler("/Home/Error");
                app.UseHsts();
            }

            app.UseHttpsRedirection();
            app.UseStaticFiles();

            app.UseRouting();

            app.UseAuthorization();

            app.UseEndpoints(endpoints =>
            {
                endpoints.MapControllerRoute(
                    name: "default",
                    pattern: "{controller=Home}/{action=Index}/{id?}");
            });
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
