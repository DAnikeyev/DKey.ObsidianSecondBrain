---
date_added: 2025-03-13
tags:
  - csharp
---
Up: [Controller in Asp.Net](Controller%20in%20Asp.Net.md)
___
 Is a [MiddleWare in WepApi](MiddleWare%20in%20WepApi.md) Model validation in ASP.NET Core ensures that incoming data conforms to expected formats, values, and business rules before processing it further. The framework provides several features to support robust validation with minimal code. Here’s an overview:

1. Built-in Data Annotations:  
    ASP.NET Core supports a variety of built-in validation attributes provided by the System.ComponentModel.DataAnnotations namespace, such as [Required], [Range], [StringLength], [EmailAddress], etc. These attributes can be applied directly to model properties.
    
2. Automatic Validation with [ApiController]:  
    When using the [ApiController] attribute on a controller, model validation errors are automatically checked after binding. If the model state is invalid, the framework returns an appropriate error response (400 Bad Request) without needing explicit checks in the action.
    
3. Custom ValidationAttributes:  
    You can create your own validation logic by extending the ValidationAttribute class to enforce custom rules. These attributes can be applied to properties much like built-in attributes.
    
4. IValidatableObject Interface:  
    For complex validation scenarios that involve multiple properties or business logic conditions, you can implement the IValidatableObject interface on a model. This approach allows you to return multiple ValidationResults based on custom conditions.
    
5. Error Messages and Localization:  
    Custom error messages can be provided via attributes, and ASP.NET Core supports localization for validation messages, making it easier to work in multi-language environments.

## Examples
#### Validation Attributes
```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class FutureDateAttribute : ValidationAttribute
{
    // Custom validation attribute to ensure a DateTime value is in the future.
    public override bool IsValid(object value)
    {
        if (value is DateTime dateValue)
        {
            return dateValue > DateTime.Now;
        }
        return false; // Not a valid date.
    }
}
```

### Required Attribute
```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Appointment
{
    [Required(ErrorMessage = "Title is required.")]
    public string Title { get; set; }

    [FutureDate(ErrorMessage = "The appointment date must be in the future.")]
    public DateTime AppointmentDate { get; set; }
}
```


### Manual Validation

When a POST request (or any appropriate HTTP method) is made to the endpoint (for example, /Event), the framework will:

- Bind the request body to an instance of Event.
- Run the built-in and custom validations.
- Populate ModelState with any errors if validations fail.


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
