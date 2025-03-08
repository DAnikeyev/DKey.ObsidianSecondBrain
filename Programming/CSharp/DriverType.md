---
date_added: 2025-03-08
tags:
  - csharp
---
Up: [DriveInfo](DriveInfo.md)
___
types of drivers

| Name            | Value | Description                                                         |
| --------------- | ----- | ------------------------------------------------------------------- |
| Unknown         | 0     | The type of drive is unknown.                                       |
| NoRootDirectory | 1     | The drive does not have a root directory.                           |
| Removable       | 2     | The drive is a removable storage device, such as a USB flash drive. |
| Fixed           | 3     | The drive is a fixed disk.                                          |
| Network         | 4     | The drive is a network drive.                                       |
| CDRom           | 5     | The drive is an optical disc device, such as a CD or DVD-ROM.       |
| Ram             | 6     | The drive is a RAM disk.                                            |

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
