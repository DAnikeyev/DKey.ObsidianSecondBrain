---
date_added: 2025-03-03
tags:
  - csharp
---
Up: [Fundamental Interfaces](Fundamental%20Interfaces.md)
___
 INotifyPropertyChanged is an interface defined in the System.ComponentModel namespace. It is used primarily in data binding scenarios (for example in WPF, Xamarin, or UWP) to notify the UI or other components when a property value has changed. This enables the user interface to automatically update whenever the underlying data changes.
```cs
using System;
using System.ComponentModel;
using System.Runtime.CompilerServices;

namespace ExampleApp
{
    public class PersonViewModel : INotifyPropertyChanged
    {
        private string _name;

        public event PropertyChangedEventHandler PropertyChanged;

        public string Name
        {
            get => _name;
            set
            {
                if (_name != value)
                {
                    _name = value;
                    OnPropertyChanged();
                }
            }
        }

        // This method notifies subscribers about property changes.
        protected void OnPropertyChanged([CallerMemberName] string propertyName = null)
        {
            PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            var person = new PersonViewModel();
            // Subscribe to the PropertyChanged event.
            person.PropertyChanged += (sender, e) =>
            {
                Console.WriteLine($"Property {e.PropertyName} has changed.");
            };

            // Changing the property triggers the PropertyChanged event.
            person.Name = "Alice";
            person.Name = "Bob";
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
