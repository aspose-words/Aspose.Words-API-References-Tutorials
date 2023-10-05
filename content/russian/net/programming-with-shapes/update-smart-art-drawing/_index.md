---
title: Обновить Smart Art Drawing
linktitle: Обновить Smart Art Drawing
second_title: API обработки документов Aspose.Words
description: Узнайте, как обновить рисунок Smart Art в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/update-smart-art-drawing/
---

В этом руководстве объясняется, как обновить рисунок Smart Art в документе Word с помощью Aspose.Words для .NET. Перебирая фигуры в документе и проверяя, есть ли у них Smart Art, вы можете обновить рисунок Smart Art, чтобы отразить любые изменения, внесенные в его данные.

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
Загрузите документ Word, содержащий рисунок Smart Art, с помощью`Document` конструктор класса.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Шаг 3. Обновите рисунок Smart Art.
 Перебирайте фигуры в документе, используя`GetChildNodes` метод с`NodeType.Shape` параметр. Проверьте, есть ли у каждой фигуры Smart Art, используя`HasSmartArt` собственности, и если это правда, позвоните в`UpdateSmartArtDrawing` метод обновления рисунка Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Пример исходного кода для обновления Smart Art Drawing с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Вот и все! Вы успешно обновили рисунок Smart Art в своем документе Word с помощью Aspose.Words для .NET.