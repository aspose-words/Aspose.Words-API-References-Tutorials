---
title: Пробел между азиатским и латинским текстом
linktitle: Пробел между азиатским и латинским текстом
second_title: API обработки документов Aspose.Words
description: Узнайте, как автоматически настроить расстояние между азиатским и латинским текстом в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/space-between-asian-and-latin-text/
---

В этом уроке мы собираемся показать вам, как использовать функцию пробела между азиатским и латинским текстом с Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и применить изменения.

## Шаг 1: Создание и настройка документа

Для начала создайте новый документ и связанный с ним объект DocumentBuilder. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Настройка пробела между азиатским и латинским текстом

Теперь мы настроим пространство между азиатским и латинским текстом, используя свойства объекта ParagraphFormat. Вот как:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Шаг 3: Сохранение документа

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Пример исходного кода для пробела между азиатским и латинским текстом с использованием Aspose.Words для .NET

Вот полный исходный код для функции пробела между азиатским и латинским текстом с Aspose.Words для .NET:


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

С помощью этого кода вы сможете автоматически регулировать расстояние между азиатским и латинским текстом в документе с помощью Aspose.Words для .NET.



