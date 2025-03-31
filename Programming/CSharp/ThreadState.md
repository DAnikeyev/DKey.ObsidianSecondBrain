---
date_added: 2025-03-05
tags:
  - csharp
---
Up: [[Thread]]
___
![](Pasted%20image%2020250324053118.png)

| Name        | Value | Description                                                                                                                                                                                                      |
| ----------- | ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Initialized | 0     | A state that indicates the thread has been initialized, but has not yet started.                                                                                                                                 |
| Ready       | 1     | A state that indicates the thread is waiting to use a processor because no processor is free. The thread is prepared to run on the next available processor.                                                     |
| Running     | 2     | A state that indicates the thread is currently using a processor.                                                                                                                                                |
| Standby     | 3     | A state that indicates the thread is about to use a processor. Only one thread can be in this state at a time.                                                                                                   |
| Terminated  | 4     | A state that indicates the thread has finished executing and has exited.                                                                                                                                         |
| Wait        | 5     | A state that indicates the thread is not ready to use the processor because it is waiting for a peripheral operation to complete or a resource to become free. When the thread is ready, it will be rescheduled. |
| Transition  | 6     | A state that indicates the thread is waiting for a resource, other than the processor, before it can execute. For example, it might be waiting for its execution stack to be paged in from disk.                 |
| Unknown     | 7     | The state of the thread is unknown.                                                                                                                                                                              |
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
