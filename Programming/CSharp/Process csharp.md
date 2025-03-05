---
date_added: 2025-03-04
tags:
  - csharp
---
Up: [Process](Processes/Process.md) [System.Diagnostics](System.Diagnostics.md)
___
Provides access to local and remote processes and enables you to start and stop local system processes.

>[!Info]
> Implements [IDisposable](IDisposable.md)
## Properties
| Property        | Description                                                                                                                                                                                           |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ExitTime        | This property allows you to retrieve the timestamp associated with a process that has exited (represented by DateTime).                                                                               |
| Handle          | This property returns the handle (represented by IntPtr) assigned to the process by the operating system. It can be useful when building .NET applications that need to interact with unmanaged code. |
| Id              | This property allows you to get the identifier (PID) of the corresponding process.                                                                                                                    |
| MachineName     | This property allows you to get the name of the computer on which the corresponding process is running.                                                                                               |
| MainWindowTitle | This property allows you to get the title of the main window of the process (if the process has no main window, an empty string is returned).                                                         |
| Modules         | This property allows you to access a strongly typed ProcessModuleCollection representing the set of modules (*.dll or *.exe) that have been loaded within the current process.                        |
| ProcessName     | This property allows you to get the name of the process (which, as expected, matches the name of the application itself).                                                                             |
| Responding      | This property allows you to get a value indicating whether the user interface of the process is responding to user input (or is currently in a "hung" state).                                         |
| StartTime       | This property allows you to get the time when the process was started (represented by DateTime).                                                                                                      |
| [[Thread]]s     | This property allows you to get the set of threads running in the specified process (represented by a collection of ProcessThread objects).                                                           |

## Methods

| Method              | Description                                                                                           |
| ------------------- | ----------------------------------------------------------------------------------------------------- |
| CloseMainWindow()   | This method closes a process with a user interface by sending a close message to its main window.     |
| GetCurrentProcess() | This static method returns a new Process object representing the process that is currently active.    |
| GetProcesses()      | This static method returns an array of new Process objects that are running on the specified machine. |
| Kill()              | This method immediately stops the specified process.                                                  |
| Start()             | This method starts a process.                                                                         |
User Account Control (UAC) can further restrict the ability to terminate processes.

```cs
                using (Process myProcess = new Process())
                {
                    myProcess.StartInfo.UseShellExecute = false;
                    // You can start any process, HelloWorld is a do-nothing example.
                    myProcess.StartInfo.FileName = "C:\\HelloWorld.exe";
                    myProcess.StartInfo.CreateNoWindow = true;
                    myProcess.Start();
                }
```


# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
