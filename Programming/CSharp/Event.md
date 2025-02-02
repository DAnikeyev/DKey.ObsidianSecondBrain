---
date_added: 2025-01-23
tags:
  - csharp
---
Up: [CSharp Operator](CSharp%20Operator.md)
___
 An _**event**_ is a member that enables an object to trigger notifications. Event users can attach executable code for events by supplying **event handlers**.

Publisher has its own event, and the subscribers can subscribe to the event. When the publisher raises the event, the subscriber's event handler is called.

## Event keyword

Is actually not required, using [[Action]] or a [[delegate]] is enough. event keyword prevents invoking the event outside of the class and also add event accesssors functionality.


## Example
 ```cs
 public class SampleEventArgs
{
    public SampleEventArgs(string text) { Text = text; }
    public string Text { get; } // readonly
}

public class Publisher
{
    // Declare the delegate (if using non-generic pattern).
    public delegate EventHandler SampleEventHandler(object sender, DataEventArgs e);
    
	public void TestEventParser((object sender, DataEventArgs e)
	{
		Console.WriteLine($"DataEventArgs: {e.Value}");
		// Unsuscribe the event
		SampleEvent -= TestEventParser;
	}
	
    // Declare the event.
    public event EventHandler SampleEvent;

	public void Init
	{
		SampleEvent += TestEventParser;
	}
    // Wrap the event in a protected virtual method
    // to enable derived classes to raise the event.
    protected virtual void RaiseSampleEvent()
    {
        // Raise the event in a thread-safe manner using the ?. operator.
        SampleEvent?.Invoke(this, new SampleEventArgs("Hello"));
    }


    public class DataEventArgs : EventArgs
    {
        public string Value { get; set; }
    }
}
```
You can also use the generic pattern for the delegate:
```cs
    public event EventHandler<DataEventArgs> SampleEventHandler;
```

Custom event type using delegate
```cs
public class Publisher
{
    public delegate void SampleEventHandler(float f);
    public event SampleEventHandler SampleEvent;

    protected virtual void RaiseSampleEvent()
    {
        SampleEvent?.Invoke(this, 3f);
    }
}

```
Or Action
```cs
public class Publisher
{
    public event Action<float> SampleEvent;

    protected virtual void RaiseSampleEvent()
    {
        SampleEvent?.Invoke(3f);
    }
}
```

## Subscribing
```cs
//Using Assignment
publisher.RaiseCustomEvent += HandleCustomEvent;
//Using Anonymous method
publisher.RaiseCustomEvent += (sender, e) => { Console.WriteLine($"DataEventArgs: {e.Value}"); };
```
Is a delegate in  System namespace with arguments of type object and a class derived from EventArgs. The event handler is a method that is called when the event is raised.

## Derived class event handling

```cs
    // Base class event publisher
    public abstract class Shape
    {
        protected double _area;

        public double Area
        {
            get => _area;
            set => _area = value;
        }

        // The event. Note that by using the generic EventHandler<T> event type
        // we do not need to declare a separate delegate type.
        public event EventHandler<ShapeEventArgs> ShapeChanged;

        public abstract void Draw();

        //The event-invoking method that derived classes can override.
        protected virtual void OnShapeChanged(ShapeEventArgs e)
        {
            // Safely raise the event for all subscribers
            ShapeChanged?.Invoke(this, e);
        }
    }

    public class Circle : Shape
    {
        private double _radius;

        public Circle(double radius)
        {
            _radius = radius;
            _area = 3.14 * _radius * _radius;
        }

        public void Update(double d)
        {
            _radius = d;
            _area = 3.14 * _radius * _radius;
            OnShapeChanged(new ShapeEventArgs(_area));
        }

        protected override void OnShapeChanged(ShapeEventArgs e)
        {
            // Do any circle-specific processing here.

            // Call the base class event invocation method.
            base.OnShapeChanged(e);
        }

        public override void Draw()
        {
            Console.WriteLine("Drawing a circle");
        }
    }
```

## Custom event Accessors

using the `add` and `remove` accessors, you can customize the behavior of the event when subscribers are added or removed. This is useful for logging, debugging, or enforcing custom rules.
```cs
using System;

public class BaseClass
{
    // Declare a protected virtual event
    protected virtual event EventHandler SomeEvent;

    // Method to raise the event within the base class
    protected virtual void OnSomeEvent()
    {
        SomeEvent?.Invoke(this, EventArgs.Empty);
    }

    public void TriggerEvent()
    {
        // Public method to indirectly raise the protected event
        OnSomeEvent();
    }
}

public class DerivedClass : BaseClass
{
    // Override the protected virtual event (using the same name is allowed)
    protected override event EventHandler SomeEvent
    {
        add
        {
            Console.WriteLine("DerivedClass: Adding an event handler.");
            base.SomeEvent += value;
        }
        remove
        {
            Console.WriteLine("DerivedClass: Removing an event handler.");
            base.SomeEvent -= value;
        }
    }

    // Optionally override the protected virtual method that raises the event
    protected override void OnSomeEvent()
    {
        Console.WriteLine("DerivedClass: Before raising the base event.");
        base.OnSomeEvent(); // Raise the base event
        Console.WriteLine("DerivedClass: After raising the base event.");
    }
}
```
## Protected virtual event
As in the example above, you can declare an event as protected virtual in the base class and override it in the derived class. Event is only accessible within the class and its derived classes.

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
