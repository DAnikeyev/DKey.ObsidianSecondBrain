---
date_added: 2025-03-08
tags:
  - csharp
---
Up: [System.IO](System.IO.md)
___

Provides access to information on a drive.

| Member                          | Type       | Description                                                                 |
|---------------------------------|------------|-----------------------------------------------------------------------------|
| `DriveInfo`                     | Constructor| Initializes a new instance of the `DriveInfo` class for a specified drive.  |
| `Name`                          | Property   | Gets the name of the drive (e.g., "C:\").                                  |
| `DriveType`                     | Property   | Gets the type of the drive (e.g., `Fixed`, `Removable`, `Network`).        |
| `DriveFormat`                   | Property   | Gets the file system format of the drive (e.g., "NTFS", "FAT32").          |
| `IsReady`                       | Property   | Gets a value indicating whether the drive is ready to be accessed.         |
| `AvailableFreeSpace`            | Property   | Gets the amount of available free space on the drive, in bytes.            |
| `TotalFreeSpace`                | Property   | Gets the total amount of free space available on the drive, in bytes.      |
| `TotalSize`                     | Property   | Gets the total size of storage space on the drive, in bytes.               |
| `VolumeLabel`                   | Property   | Gets or sets the volume label of the drive.                                |
| `RootDirectory`                 | Property   | Gets the root directory of the drive.                                      |
| `GetDrives()`                   | Method     | Returns a `DriveInfo` array representing all logical drives on the computer. |


```cs
using System;
using System.IO;

class Test
{
    public static void Main()
    {
        DriveInfo[] allDrives = DriveInfo.GetDrives();

        foreach (DriveInfo d in allDrives)
        {
            Console.WriteLine("Drive {0}", d.Name);
            Console.WriteLine("  Drive type: {0}", d.DriveType);
            if (d.IsReady)
            {
                Console.WriteLine("  Volume label: {0}", d.VolumeLabel);
                Console.WriteLine("  File system: {0}", d.DriveFormat);
                Console.WriteLine(
                    "  Available space to current user:{0, 15} bytes",
                    d.AvailableFreeSpace);

                Console.WriteLine(
                    "  Total available space:          {0, 15} bytes",
                    d.TotalFreeSpace);

                Console.WriteLine(
                    "  Total size of drive:            {0, 15} bytes ",
                    d.TotalSize);
            }
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
