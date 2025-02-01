---
date_added: 2025-02-01
tags:
  - csharp
---
Up: [[Task]]
___
 **What is TaskScheduler?**  
TaskScheduler is a class in C# that manages how and when tasks are executed. It's part of the Task Parallel Library (TPL) and provides mechanisms to control task execution, including scheduling, prioritization, and synchronization of tasks.

**Key Concepts:**

1. **Default Scheduler**: Every application has a default TaskScheduler (ThreadPoolTaskScheduler) that schedules tasks to run on the thread pool.
2. **Current Scheduler**: Tasks inherit their scheduler from the context they're created in.
3. **Custom Schedulers**: You can create custom schedulers for specific needs (like UI thread execution).
 
 The default task scheduler provides work-stealing for load-balancing, thread injection/retirement for maximum throughput, and overall good performance. It should be sufficient for most scenarios.

 ```csharp
 public abstract class TaskScheduler{
     public static TaskScheduler Default { get; }
     public static TaskScheduler Current { get; }
     public static TaskScheduler FromCurrentSynchronizationContext();
     public virtual int MaximumConcurrencyLevel { get; }
     public virtual void QueueTask(Task task);
     public virtual bool TryExecuteTaskInline(Task task, bool taskWasPreviouslyQueued);
     public virtual bool TryDequeue(Task task);
 }
 ```

 ```
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
