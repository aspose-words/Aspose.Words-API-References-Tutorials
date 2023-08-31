---
title: Обновить интеллектуальный художественный рисунок
linktitle: Обновить интеллектуальный художественный рисунок
second_title: API обработки документов Aspose.Words
description: Узнайте, как обновить рисунок Smart Art в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/update-smart-art-drawing/
---

В этом руководстве объясняется, как обновить рисунок Smart Art в документе Word с помощью Aspose.Words для .NET. Перебирая фигуры в документе и проверяя, есть ли в них Smart Art, вы можете обновить рисунок Smart Art, чтобы отразить любые изменения, внесенные в его данные.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и Word Processing с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ
 Загрузите документ Word, содержащий рисунок Smart Art, с помощью`Document` конструктор класса.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Шаг 3. Обновите рисунок Smart Art
 Перебирайте фигуры в документе, используя`GetChildNodes` метод с`NodeType.Shape` параметр. Проверьте, есть ли у каждой фигуры Smart Art, используя`HasSmartArt` свойство, и если оно истинно, вызвать`UpdateSmartArtDrawing` метод обновления рисунка Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Пример исходного кода для обновления рисунка Smart Art с помощью Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Вот и все! Вы успешно обновили рисунок Smart Art в документе Word с помощью Aspose.Words for .NET.