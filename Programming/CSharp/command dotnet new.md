---
date_added: 2025-02-08
tags:
  - csharp
---
Up: [DotNet CLI (Command Line Interface)](DotNet%20CLI%20(Command%20Line%20Interface).md)
___
 ```cs
 dotnet new <TEMPLATE> [--dry-run] [--force] [-lang|--language {"C#"|"F#"|VB}]
    [-n|--name <OUTPUT_NAME>] [-f|--framework <FRAMEWORK>] [--no-update-check]
    [-o|--output <OUTPUT_DIRECTORY>] [--project <PROJECT_PATH>]
    [-d|--diagnostics] [--verbosity <LEVEL>] [Template options]

dotnet new -h|--help
```

The following table shows the templates that come pre-installed with the .NET SDK. The default language for the template is shown inside the brackets. Click on the short name link to see the specific template options.

| Templates                                    | Short name                                                                                                    | Tags                                  | Introduced       |
| -------------------------------------------- | ------------------------------------------------------------------------------------------------------------- | ------------------------------------- | ---------------- |
| Console Application                          | [`console`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#console)             | Common/Console                        | 1.0              |
| Class library                                | [`classlib`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#classlib)           | Common/Library                        | 1.0              |
| WPF Application                              | [`wpf`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#wpf)                     | Common/WPF                            | 3.0 (5.0 for VB) |
| WPF Class library                            | [`wpflib`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#wpf)                  | Common/WPF                            | 3.0 (5.0 for VB) |
| WPF Custom Control Library                   | [`wpfcustomcontrollib`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#wpf)     | Common/WPF                            | 3.0 (5.0 for VB) |
| WPF User Control Library                     | [`wpfusercontrollib`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#wpf)       | Common/WPF                            | 3.0 (5.0 for VB) |
| Windows Forms (WinForms) Application         | [`winforms`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#winforms)           | Common/WinForms                       | 3.0 (5.0 for VB) |
| Windows Forms (WinForms) Class library       | [`winformslib`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#winforms)        | Common/WinForms                       | 3.0 (5.0 for VB) |
| Worker Service                               | [`worker`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#web-others)           | Common/Worker/Web                     | 3.0              |
| MSTest Test Project                          | [`mstest`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#mstest)               | Test/MSTest                           | 1.0              |
| MSTest Test Class                            | [`mstest-class`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#mstest-class)   | Test/MSTest                           | 1.0              |
| NUnit 3 Test Project                         | [`nunit`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#nunit)                 | Test/NUnit                            | 2.1.400          |
| NUnit 3 Test Item                            | `nunit-test`                                                                                                  | Test/NUnit                            | 2.2              |
| xUnit Test Project                           | [`xunit`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#xunit)                 | Test/xUnit                            | 1.0              |
| Razor Component                              | `razorcomponent`                                                                                              | Web/ASP.NET                           | 3.0              |
| Razor Page                                   | [`page`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#page)                   | Web/ASP.NET                           | 2.0              |
| MVC ViewImports                              | [`viewimports`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#namespace)       | Web/ASP.NET                           | 2.0              |
| MVC ViewStart                                | `viewstart`                                                                                                   | Web/ASP.NET                           | 2.0              |
| Blazor Web App                               | [`blazor`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#blazor)               | Web/Blazor                            | 8.0.100          |
| Blazor WebAssembly Standalone App            | [`blazorwasm`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#blazorwasm)       | Web/Blazor/WebAssembly/PWA            | 3.1.300          |
| ASP.NET Core Empty                           | [`web`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#web)                     | Web/Empty                             | 1.0              |
| ASP.NET Core Web App (Model-View-Controller) | [`mvc`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#web-options)             | Web/MVC                               | 1.0              |
| ASP.NET Core Web App                         | [`webapp, razor`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#web-options)   | Web/MVC/Razor Pages                   | 2.2, 2.0         |
| Razor Class Library                          | [`razorclasslib`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#razorclasslib) | Web/Razor/Library/Razor Class Library | 2.1              |
| ASP.NET Core Web API                         | [`webapi`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#webapi)               | Web/Web API/API/Service/WebAPI        | 1.0              |
| ASP.NET Core API                             | [`webapiaot`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#webapiaot)         | Web/Web API/API/Service               | 8.0              |
| ASP.NET Core API controller                  | [`apicontroller`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#apicontroller) | Web/ASP.NET                           | 8.0              |
| ASP.NET Core gRPC Service                    | [`grpc`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#web-others)             | Web/gRPC                              | 3.0              |
| dotnet gitignore file                        | `gitignore`                                                                                                   | Config                                | 3.0              |
| global.json file                             | [`globaljson`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#globaljson)       | Config                                | 2.0              |
| NuGet Config                                 | `nugetconfig`                                                                                                 | Config                                | 1.0              |
| Dotnet local tool manifest file              | `tool-manifest`                                                                                               | Config                                | 3.0              |
| Web Config                                   | `webconfig`                                                                                                   | Config                                | 1.0              |
| Solution File                                | `sln`                                                                                                         | Solution                              | 1.0              |
| Protocol Buffer File                         | [`proto`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#namespace)             | Web/gRPC                              | 3.0              |
| EditorConfig file                            | [`editorconfig`](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-new-sdk-templates#editorconfig)   | Config                                | 6.0              |


 >[!Note]
>Starting with the .NET 7 SDK, the `dotnet new` syntax has changed:
>
>- The `--list`, `--search`, `--install`, and `--uninstall` options became `list`, `search`,
>- `install`, and `uninstall` subcommands.
> - The `--update-apply` option became the `update` subcommand.
> - To use `--update-check`, use the `update` subcommand with the `--check-only` option.
> 
>Other options that were available before are still available to use with their respective subcommands. Separate help for each subcommand is available via the `-h` or `--help` option: `dotnet new <subcommand> --help` lists all supported options for the subcommand
>
>Additionally, tab completion is now available for `dotnet new`. It supports completion for installed template names and for the options a selected template provides. To activate tab completion for the .NET SDK, see [Enable tab completion](https://learn.microsoft.com/en-us/dotnet/core/tools/enable-tab-autocomplete).

# Subcommands
-  `dotnet new list` - Lists available templates to be run using `dotnet new`.
- `dotnet new search` - searches for the templates supported by `dotnet new` on NuGet.org.
- `dotnet new details` - Displays template package metadata.
- `dotnet new install` - installs a template package.
- `dotnet new uninstall` - uninstalls a template package.
- `dotnet new update` - updates installed template packages.
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
