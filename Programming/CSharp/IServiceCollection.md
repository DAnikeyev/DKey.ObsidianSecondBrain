---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [IWebHostBuilder](IWebHostBuilder.md)
___
 Is used in startup:
  ```csharp
   
public class Startup  
{  
    public IConfiguration Configuration { get; }  
  
    public Startup(IConfiguration configuration)  
    {        Configuration = configuration;  
    }  
    public void ConfigureServices(IServiceCollection services)  
    {        // Configure database  
        services.AddDbContext<GameDbContext>(options =>  
        {  
            options.UseNpgsql(Configuration.GetConnectionString("DefaultConnection"));  
        });
          
        // Register repositories  
        services.AddScoped<IGameRepository, GameRepository>();  
  
        // Add routing capabilities  
        services.AddRouting();  
  
        // Configure HTTPS  
        services.AddHttpsRedirection(options =>  
        {  
            options.HttpsPort = 5001; // Set your HTTPS port here  
            options.RedirectStatusCode = StatusCodes.Status307TemporaryRedirect;  
        });    }  
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)  
    {        app.UseHttpsRedirection();  
  
        // Initialize the database  
        DbInitializer.Initialize(app.ApplicationServices);  
  
        // Configure routing  
        app.UseRouter(routes =>  
        {
        ...
 ```

### Key Features of IServiceCollection

1. **Service Registration**: It allows you to register services with various lifetimes:
    
    - `AddSingleton<T>()`: Creates a single instance throughout the application's lifetime
    - `AddScoped<T>()`: Creates a new instance for each request/scope
    - `AddTransient<T>()`: Creates a new instance each time the service is requested
    - `AddDbContext()`: Adds a scoped DbContext service
    

2. **Extension Methods**: The interface is extensible through extension methods, allowing frameworks and libraries to add their own registration mechanisms (like `AddControllers()`, `AddMvc()`, etc.)
    
3. **Service Provider Creation**: Once configured, IServiceCollection is used to build an IServiceProvider, which resolves dependencies at runtime
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
