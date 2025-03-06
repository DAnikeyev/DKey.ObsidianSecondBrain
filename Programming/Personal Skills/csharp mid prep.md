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
- ```Атрибут следует рассматривать как логический контейнер состояния. Иначе говоря, хотя атрибут и является классом, этот класс должен быть крайне простым. Он должен содержать всего один открытый конструктор, принимающий обязательную (или позиционную) информацию о состоянии атрибута. Также класс может содержать открытые поля/свойства, принимающие дополнительную (или именованную) информацию о состоянии атрибута. В классе не должно быть открытых методов, событий или других членов.``` - Контрпримеры: NUnit, [Validation framework](Validation%20framework.md)



```
## Темы которые менее полезны чем список ниже и присутствуют в МК (В т.ч. опосредованно):
- Constrained Execution Region
- Code contracts
## Темы, которые более полезны чем список выше и отсутствуют в МК:

 - Synchronisation primitives
# Links
```dataview
LIST
FROM [[]]
WHERE contains(file.name, "")
SORT file.name ASC
```
