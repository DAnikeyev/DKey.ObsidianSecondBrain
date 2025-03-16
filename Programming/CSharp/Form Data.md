---
date_added: 2025-03-14
tags:
  - csharp
---
Up: [HTTP](HTTP.md) [ASP.NET Core](ASP.NET%20Core.md)
___
In the context of web development, a "form" is an HTML element that allows users to input data and submit it to a server for processing.

- **GetForm Method**: Generates an HTML form with a text input and a submit button. The form uses the POST method.
- **ShowForm Method**: Processes the form data when the form is submitted. It checks if the request has form content, iterates through the form keys, and appends them to a `StringBuilder`.
- **HttpRequest**: Used to determine the HTTP method and access form data.
- **IFormCollection**: Represents the collection of form data sent to the server.

This code is structured to handle both GET and POST requests, generating a form for GET requests and processing form data for POST requests.

```cs
public static string GetForm(HttpRequest request)
{
    string result = string.Empty;

    // Determine the HTTP method and call the appropriate method
    switch (request.Method)
    {
        case "GET":
            result = GetForm();
            break;
        case "POST":
            result = ShowForm(request);
            break;
        default:
            break;
    }

    return result;
}

// Method to generate the HTML form
private static string GetForm() =>
    "<form method=\"post\" action=\"form\">" +
    "<input type=\"text\" name=\"text1\" />" +
    "<input type=\"submit\" value=\"Submit\" />" +
    "</form>";

// Method to process and display form data
private static string ShowForm(HttpRequest request)
{
    var sb = new StringBuilder();

    // Check if the request contains form data
    if (request.HasFormContentType)
    {
        IFormCollection coll = request.Form;

        // Iterate through the form keys and append them to the StringBuilder
        foreach (var key in coll.Keys)
        {
            sb.Append(key.Div(HtmlEncoder.Default.Encode(coll[key])));
        }

        return sb.ToString();
    }
    else
    {
        return "no form".Div();
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
