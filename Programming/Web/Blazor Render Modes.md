---
date_added: 2024-11-24
tags:
  - blazor
  - web
---
Up: [Blazor](Blazor.md)
___
 Every [Blazor component](Blazor%20component) adopts a render mode to determine where it's rendered and whether or not it's interactive

# Modes
---

| Name                    | Description                                                                                                            | Render location     | Interactive |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------- | ------------------- | ----------- |
| Static Server           | Static server-side rendering (static SSR)                                                                              | Server              | ❌No         |
| Interactive Server      | Interactive server-side rendering (interactive SSR) using Blazor Server.                                               | Server              | ✔️Yes       |
| Interactive WebAssembly | Client-side rendering (CSR) using Blazor WebAssembly†.                                                                 | Client              | ✔️Yes       |
| Interactive Auto        | Interactive SSR using Blazor Server initially and then CSR on subsequent visits after the Blazor bundle is downloaded. | Server, then client | ✔️Yes       |


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
