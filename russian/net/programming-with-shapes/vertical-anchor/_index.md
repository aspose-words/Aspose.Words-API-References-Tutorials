---
title: Вертикальный анкер
linktitle: Вертикальный анкер
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как расположить фигуру вертикально в документе, используя функцию вертикальной привязки в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/vertical-anchor/
---

В этом руководстве объясняется, как использовать функцию вертикальной привязки в Aspose.Words для .NET для вертикального размещения фигуры в документе. Установив свойство вертикальной привязки фигуры, вы можете управлять ее выравниванием по вертикали относительно текста или страницы.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и работы с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"`с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Создайте новый документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект для работы с документом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте и настройте фигуру
 Вставьте фигуру в документ, используя`InsertShape` метод`DocumentBuilder` объект. Установите желаемые размеры формы.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Шаг 4: Установите вертикальную привязку
Задайте свойство вертикальной привязки фигуры, чтобы управлять ее выравниванием по вертикали. В этом примере мы устанавливаем значение «Нижний», чтобы привязать фигуру к нижней части текста или страницы.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Шаг 5: Добавьте содержимое в форму
 Использовать`MoveTo` метод`DocumentBuilder` объект, чтобы переместить курсор к первому абзацу фигуры. Затем используйте`Write` способ добавления содержимого в форму.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithShapes.VerticalAnchor.docx».

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Пример исходного кода для вертикальной привязки с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Вот и все! Вы успешно использовали функцию вертикальной привязки в Aspose.Words для .NET для вертикального размещения фигуры в документе.