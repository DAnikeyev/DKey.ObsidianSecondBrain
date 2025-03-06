---
date_added: 2025-03-06
tags:
  - csharp
---
Up: [CSharp](CSharp.md)
___
 ```cs
 using System;
using System.Collections.Generic;
using System.Linq;
using System.Reflection;

// Validation attributes
[AttributeUsage(AttributeTargets.Property, AllowMultiple = true)]
public abstract class ValidationAttribute : Attribute
{
    public string ErrorMessage { get; set; }
    
    public abstract bool IsValid(object value);
}

public class RequiredAttribute : ValidationAttribute
{
    public RequiredAttribute()
    {
        ErrorMessage = "Value is required";
    }
    
    public override bool IsValid(object value)
    {
        return value != null && !string.IsNullOrWhiteSpace(value.ToString());
    }
}

public class StringLengthAttribute : ValidationAttribute
{
    public int MinLength { get; set; }
    public int MaxLength { get; set; }
    
    public StringLengthAttribute(int minLength, int maxLength)
    {
        MinLength = minLength;
        MaxLength = maxLength;
        ErrorMessage = $"String must be between {MinLength} and {MaxLength} characters";
    }
    
    public override bool IsValid(object value)
    {
        if (value == null)
            return MinLength == 0;
            
        string strValue = value.ToString();
        return strValue.Length >= MinLength && strValue.Length <= MaxLength;
    }
}

public class RangeAttribute : ValidationAttribute
{
    public int Min { get; set; }
    public int Max { get; set; }
    
    public RangeAttribute(int min, int max)
    {
        Min = min;
        Max = max;
        ErrorMessage = $"Value must be between {Min} and {Max}";
    }
    
    public override bool IsValid(object value)
    {
        if (value == null)
            return false;
            
        if (int.TryParse(value.ToString(), out int intValue))
        {
            return intValue >= Min && intValue <= Max;
        }
        
        return false;
    }
}

// Validation engine
public class Validator
{
    public static List<string> Validate(object instance)
    {
        var errors = new List<string>();
        var type = instance.GetType();
        
        foreach (var property in type.GetProperties())
        {
            var value = property.GetValue(instance);
            var validationAttributes = property.GetCustomAttributes<ValidationAttribute>();
            
            foreach (var attribute in validationAttributes)
            {
                if (!attribute.IsValid(value))
                {
                    errors.Add($"{property.Name}: {attribute.ErrorMessage}");
                }
            }
        }
        
        return errors;
    }
}

// Example model with validation attributes
public class User
{
    [Required]
    [StringLength(3, 50)]
    public string Username { get; set; }
    
    [Required]
    [StringLength(8, 20)]
    public string Password { get; set; }
    
    [Range(13, 120)]
    public int Age { get; set; }
    
    [Required]
    public string Email { get; set; }
}

// Usage example
public class Program
{
    public static void Main()
    {
        // Valid user
        var validUser = new User
        {
            Username = "john_doe",
            Password = "securePass123",
            Age = 30,
            Email = "john@example.com"
        };
        
        var validUserErrors = Validator.Validate(validUser);
        Console.WriteLine("Valid User Validation:");
        if (validUserErrors.Count == 0)
        {
            Console.WriteLine("No validation errors");
        }
        else
        {
            foreach (var error in validUserErrors)
            {
                Console.WriteLine(error);
            }
        }
        
        // Invalid user
        var invalidUser = new User
        {
            Username = "a", // Too short
            Password = "weak", // Too short
            Age = 10, // Too young
            Email = null // Required
        };
        
        var invalidUserErrors = Validator.Validate(invalidUser);
        Console.WriteLine("\nInvalid User Validation:");
        foreach (var error in invalidUserErrors)
        {
            Console.WriteLine(error);
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
