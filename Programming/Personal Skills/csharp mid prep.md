---
date_added: 2025-02-27
tags:
  - note
---
Up: [Feedback](Feedback.md)
___
# Глобально: 
когда читаю какую-то информацию из источника непонятно, насколько она устарела. С гигантским объемом информации, невозможно оперативно проверять актуальность каждого утверждения. Хотелось бы новые источники. 


- Интерфейсы: неактуальная информация, например "Beginning with C# 11, an interface may declare `static abstract` and `static virtual` members as well as default method implementation." Нет 13 источника, глава 13 источника 2 тоже не о том.
- Exceptions: Рихтер: Многие программисты не знают, что для передачи исключения можно генерировать объект любого типа, поэтому они пользуются только объектами, производными от класса Exception. CompileTime error при throw new Class1(). В Рихтере много всего лишнего и неактуального в т.ч. в этой главе
- Garbage collector: 
	- неправильный источник? Должно быть книга 2. 
	- AddMemoryPressure() неправильное описание метода, аргумент - не уровень срочности, а количество unmanaged байтов в процессе.
	- "Переопределять метод Finalize() в типах структур не допускается. Это вполне логичное ограничение, поскольку структуры являются типами значений, которые изначально никогда не размещаются в куче и, следовательно, никогда не подвергаются сборке мусора."
- AppDomain
	- Unload method is obsolete, use Abort Instead.
	- Synchronisation Attribute is obsolete, use locks/monitor/ThreadSheduler SyncContext instead
- Рефлексия ( 2 глава 15) "Позднее связывание не общепринятый термин" При поиске по microsoft.learn, например, находится только такое: Delegates provide a _late binding_ mechanism in .NET. Late Binding means that you create an algorithm where the caller also supplies at least one method that implements part of the algorithm, а в книге написано про Activator.
- Boxing: "Так как неупакованные значимые типы не размещаются в куче, отведенная для
них память освобождается сразу при возвращении управления методом, в кото-
ром описан экземпляр этого типа (в отличие от ожидания уборки мусора).". **Неверно**, value-type поле класса в куче не считается упакованным, т.к. не создается отдельный объект. Либо же тут под упаковкой имеется ввиду именно переезд значения на стек, но [документация майкрософта](https://learn.microsoft.com/ru-ru/dotnet/csharp/programming-guide/types/boxing-and-unboxing) определяет боксинг по другому: 
" Упаковка представляет собой процесс преобразования [типа значения](https://learn.microsoft.com/ru-ru/dotnet/csharp/language-reference/builtin-types/value-types) в тип `object` или в любой другой тип интерфейса, реализуемый этим типом значения. Когда тип значения упаковывается общеязыковой средой выполнения (CLR), он инкапсулирует значение внутри экземпляра [System.Object](https://learn.microsoft.com/ru-ru/dotnet/api/system.object) и сохраняет его в управляемой куче."

- ```Атрибут следует рассматривать как логический контейнер состояния. Иначе говоря, хотя атрибут и является классом, этот класс должен быть крайне простым. Он должен содержать всего один открытый конструктор, принимающий обязательную (или позиционную) информацию о состоянии атрибута. Также класс может содержать открытые поля/свойства, принимающие дополнительную (или именованную) информацию о состоянии атрибута. В классе не должно быть открытых методов, событий или других членов.``` - Контрпримеры: NUnit, [Validation framework](Validation%20framework.md)


 - Потоки исполнения = потоки ("В этой главе вы познакомитесь с потоками исполнения, или просто потоки (threads)")?


## Темы с неактуальной информацией:
 - AppDomain - Неработает в .net6+ см. https://learn.microsoft.com/en-us/dotnet/core/porting/net-framework-tech-unavailable
 - 


## Некоторые полезные источники - 
 - Актуальный синтаксис - https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/
	 - В целом для любого изучаемого типа будет не лишним посмотреть информацию на learn.microsoft, там часто актуализированная информация и примеры, в т.ч. под последние фреймворки и версии языка. Например : https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/interface
	   ``` Beginning with C# 11, an interface may declare `static abstract` and `static virtual` members for all member types except fields```
 - Synchronisation vs execution context - https://devblogs.microsoft.com/dotnet/executioncontext-vs-synchronizationcontext/
 - Garbage collection - https://www.youtube.com/watch?v=upwJMz22E4w&list=PLBwwJL9lzKMY3At-QQQijfiHdsYnOQ7vY&index=3
 - Dispose pattern - https://learn.microsoft.com/en-us/dotnet/standard/garbage-collection/implementing-dispose
 - Threading best practices https://learn.microsoft.com/en-us/dotnet/standard/threading/managed-threading-best-practices
 - TAP и разные сценарии использования https://learn.microsoft.com/en-us/dotnet/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap

# Фидбек по темам:
## General
#### Темы которые хотелось бы видеть здесь:
 - Наследование. Использование ключевых слов и модификаторов override, this, base, protected, virtual, abstract, as, is, порядок инициализации и конструктора. 
	 - (C# 12 in a Nutshell, pp. 126-138) 
	 - https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/base
	 - https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/this
- `record`, `record struct`, `ref struct` 
	- https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/struct 
	 - (C# 12 in a Nutshell, pp. 142-147) 
	 - (C# 12 in a Nutshell, pp. 227-238) 
- Generics, в особенности Generic constraints, часто используется 
	- https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/generics/constraints-on-type-parameters
- Reference parameters: ref, in, out, ref readonly 
	- https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/method-parameters
#### Темы, которые хотелось бы переместить в столбец N и/или доработать 
 - AppDomain - не работает в .net6+ см. https://learn.microsoft.com/en-us/dotnet/core/porting/net-framework-tech-unavailable бросает `System.PlatformNotSupportedException: Secondary AppDomains are not supported on this platform.`
 - BinarySerialization Obsolete and risky: https://learn.microsoft.com/en-us/dotnet/standard/serialization/binaryformatter-migration-guide/ Возможно, стоит заменить на основы протобуфа или messagePack.
 - .Net Core. WebApi: Неактульный обзор в исчточнике, в новых ASP.net используют WebApplication вместо IWebHost. 
    - https://learn.microsoft.com/en-us/aspnet/core/fundamentals/apis?view=aspnetcore-6.0
    - Возможно обзора MinimalApi достаточно для базового понимания для миддла. 
    - Либо наоборот, если нужно более полное понимание сервисов, стоит изучать также grpcService https://learn.microsoft.com/en-us/aspnet/core/grpc/?view=aspnetcore-9.0  например, в нашей команде почти не используется WebApplication, но используется grpcService (Grpc.AspNetCore) через Ap.Bootstrap.
## Многопоточность
 - Повторяется тема?  Поток (System.Threading.Thread) (4 Глава 26, 27), (13) = Потоки исполнения (4 Глава 26) `"В этой главе вы познакомитесь с потоками исполнения, или просто потоки (threads)"
#### Темы, которые хотелось бы видеть здесь:`
 - Примитивы синхронизации
 - PLinq, Parallel class (C# 12 in a Nutshell, глава 22)
## Performance

#### Темы, которые хотелось бы видеть здесь:
 - ValueTask (C# 12 in a Nutshell, глава 23) 
 - `Lazy<T>`
	 - https://learn.microsoft.com/en-us/dotnet/framework/performance/lazy-initialization
 - `Span<T>/Memory<T>` (C# 12 in a Nutshell, глава 23)
 - Performance strategies. Reducing allocations and other tips.
	 - https://learn.microsoft.com/en-us/dotnet/csharp/advanced-topics/performance/
	 - https://learn.microsoft.com/en-us/dotnet/framework/performance/performance-tips
- Быстрые коллекции. SortedSet, SortedDictionary, SortedList, Immutable and Frozen collections.  
	- (C# 12 in a Nutshell, глава 7)
	- https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic?view=net-9.0

#### Темы, которые хотелось бы переместить в столбец N и/или доработать 
 - Channel
	 - По моему опыту, применяется намного реже, чем то, что указано выше. Мне кажется, что его стоит либо подвинуть в столбец N, либо добавить темы из верхнего списка.
- Профайлинг 
	- ссылка на исчтоник не работает[Обзор ASP.NET профайлеров](https://habr.com/ru/post/109418/) 
	- можно, например, добавить BenchmarkDotnet https://benchmarkdotnet.org/articles/overview.html
- Batching - отсутствует ссылка. 

# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
