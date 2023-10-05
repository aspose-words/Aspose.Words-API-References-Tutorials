---
title: Вертикальный якорь
linktitle: Вертикальный якорь
second_title: API обработки документов Aspose.Words
description: Узнайте, как расположить фигуру вертикально в документе, используя функцию вертикальной привязки в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/vertical-anchor/
---

В этом руководстве объясняется, как использовать функцию вертикальной привязки в Aspose.Words для .NET для вертикального расположения фигуры в документе. Установив свойство вертикальной привязки фигуры, вы можете управлять ее вертикальным выравниванием относительно текста или страницы.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте новый документ и DocumentBuilder
 Создайте новый экземпляр`Document` класс и`DocumentBuilder` объект для работы с документом.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Вставьте и настройте фигуру
Вставьте фигуру в документ, используя`InsertShape` метод`DocumentBuilder` объект. Установите нужные размеры фигуры.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Шаг 4. Установите вертикальную привязку
Установите свойство вертикальной привязки фигуры, чтобы контролировать ее вертикальное выравнивание. В этом примере мы установили значение «Низ», чтобы закрепить фигуру внизу текста или страницы.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Шаг 5. Добавьте содержимое в фигуру
 Использовать`MoveTo` метод`DocumentBuilder` объект, чтобы переместить курсор к первому абзацу фигуры. Затем используйте`Write` метод добавления содержимого в фигуру.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Шаг 6: Сохраните документ
 Сохраните документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithShapes.VerticalAnchor.docx».

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Пример исходного кода для вертикальной привязки с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Вот и все! Вы успешно использовали функцию вертикальной привязки в Aspose.Words для .NET, чтобы расположить фигуру вертикально в документе.