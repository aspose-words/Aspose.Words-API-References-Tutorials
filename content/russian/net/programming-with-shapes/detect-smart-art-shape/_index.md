---
title: Обнаружение умной художественной формы
linktitle: Обнаружение умной художественной формы
second_title: API обработки документов Aspose.Words
description: Узнайте, как распознавать фигуры Smart Art в документе Word с помощью Aspose.Words для .NET, определяя графические представления.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/detect-smart-art-shape/
---

В этом руководстве объясняется, как обнаружить фигуры Smart Art в документе Word с помощью Aspose.Words для .NET. Формы Smart Art — это графические представления, используемые для визуального представления информации и идей.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ
 Загрузите документ Word, используя`Document` конструктор, передавая путь к документу в качестве параметра.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Шаг 3. Найдите умные художественные фигуры
 Перебирать дочерние узлы типа`Shape` в документе с помощью`GetChildNodes`метод. Проверьте, есть ли у каждой фигуры Smart Art, используя`HasSmart Art` свойство.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Шаг 4: Выведите результат
Распечатайте количество фигур с помощью Smart Art, обнаруженных в документе.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Пример исходного кода для обнаружения формы Smart Art с использованием Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Вот и все! Вы успешно обнаружили фигуры Smart Art в документе Word с помощью Aspose.Words для .NET.