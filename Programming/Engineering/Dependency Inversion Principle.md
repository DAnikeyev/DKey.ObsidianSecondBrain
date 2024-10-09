---
date_added: 2024-10-09
tags:
  - design
  - csharp
---
Up: [SOLID principles](SOLID%20principles.md)
___
 High-level modules should not depend on low-level modules. Both should depend on abstractions.
 
# Example
```C#
// Abstraction (interface) for sending notifications
public interface INotificationSender
{
    void Send(string message);
}

// Low-level class that implements the interface for sending emails
public class EmailService : INotificationSender
{
    public void Send(string message)
    {
        Console.WriteLine("Sending email: " + message);
    }
}

// Another low-level class that implements the interface for sending SMS
public class SMSService : INotificationSender
{
    public void Send(string message)
    {
        Console.WriteLine("Sending SMS: " + message);
    }
}

// High-level class that depends on the abstraction (not on the low-level details)
public class Notification
{
    private INotificationSender _notificationSender;

    // The high-level class now depends on an abstraction
    public Notification(INotificationSender notificationSender)
    {
        _notificationSender = notificationSender;
    }

    public void Send(string message)
    {
        _notificationSender.Send(message);
    }
}

// Example usage
class Program
{
    static void Main()
    {
        // Dependency injection - choose the appropriate implementation at runtime
        INotificationSender emailService = new EmailService();
        Notification emailNotification = new Notification(emailService);
        emailNotification.Send("Hello, email DIP!");

        INotificationSender smsService = new SMSService();
        Notification smsNotification = new Notification(smsService);
        smsNotification.Send("Hello, SMS DIP!");
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
