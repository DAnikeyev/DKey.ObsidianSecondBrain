---
date_added: 2025-03-13
tags:
  - csharp
  - web
---
Up: [IWebHost](IWebHost.md)
___
 
 IWebHostBuilder is replaced with [[WebApplicationBuilder]] in newer versions

- Provides a fluent API for configuring and building an IWebHost instance.
- It allows you to set up server settings (e.g., using Kestrel or IIS), configure services, middleware, environment settings, and logging.
- Once all configurations are applied, you call the Build() method to produce an IWebHost, which you then run.

### Create default builder:
It configures Kestrel as the web server to be used.
➤➤ The root path for the content is set to the current directory.
➤➤ Configurations are defined to load configuration from the file appsettings.json.
➤➤ An additional JSON configuration file is added with different names based on the environment:
appsettings.{environmentname}.json
➤➤ The configuration from user secrets is read when the environment name is Development.
ASP.NET Web Project ❘ 931
➤➤ The configuration settings providers are configured to load settings from environment variables and
the command line.
➤➤ The logger factory is configured to log to the console and the debug output window.
➤➤ IIS integration is enabled.

## Methods

| Method                    | Parameters                                                                     | Description                                                                               |
| ------------------------- | ------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| UseSetting                | key (string), value (string)                                                   | Sets a configuration setting that influences the host's behavior.                         |
| GetSetting                | key (string)                                                                   | Retrieves a configuration setting value.                                                  |
| UseContentRoot            | contentRoot (string)                                                           | Specifies the directory that contains the web content (views, static files, etc.).        |
| UseKestrel                | options (optional Action&lt;KestrelServerOptions&gt;)                          | Configures the host to use the Kestrel web server and optionally customize its settings.  |
| UseIISIntegration         | (no explicit parameters)                                                       | Configures the host for integration with IIS when running behind IIS/IIS Express.         |
| ConfigureAppConfiguration | configureDelegate (Action&lt;WebHostBuilderContext, IConfigurationBuilder&gt;) | Allows configuration of additional configuration sources for the host.                    |
| ConfigureServices         | configureServices (Action&lt;WebHostBuilderContext, IServiceCollection&gt;)    | Registers additional services in the host's dependency injection container.               |
| ConfigureLogging          | configureLogging (Action&lt;WebHostBuilderContext, ILoggingBuilder&gt;)        | Sets up logging providers and configuration for the host.                                 |
| CaptureStartupErrors      | captureStartupErrors (bool)                                                    | Configures the host to capture detailed errors during startup.                            |
| UseStartup                | startupType (Type) or UseStartup&lt;TStartup&gt;()                             | Specifies the startup class that defines the application's request pipeline and services. |
| Build                     | (no parameters)                                                                | Builds the IWebHost instance based on the configured settings.                            |
# Example
```cs
  
public static IWebHost BuildWebHost(string[] args) =>  
    WebHost.CreateDefaultBuilder(args)  
        .UseStartup<Startup>()  
        .Build();
  
    public class Startup  
    {  
        public void ConfigureServices(IServiceCollection services)  
        {        
        }        
        public void Configure(IApplicationBuilder app, IWebHostEnvironment env)  
        {            if (env.IsDevelopment())  
            {                app.UseDeveloperExceptionPage();  
            }            app.Run(async (context) =>  
	            {  
                await context.Response.WriteAsync("Hello World!");  
	            });        
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
