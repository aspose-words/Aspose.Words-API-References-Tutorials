---
title: Заменить строкой
linktitle: Заменить строкой
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как заменить текст строкой в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/replace-with-string/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Заменить строкой» в библиотеке Aspose.Words для .NET. Эта функция позволяет выполнять замену текста на основе определенной строки символов в документе Word.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Создание нового документа

Прежде чем мы начнем использовать замену строк, нам нужно создать новый документ, используя Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` объект:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Шаг 2. Вставьте текст в документ

 Когда у нас есть документ, мы можем вставить текст, используя`DocumentBuilder` объект. В нашем примере мы используем`Writeln` способ вставить фразу «грустный, сумасшедший плохой»:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Шаг 3. Замените строкой

 Мы используем`Range.Replace` метод замены текста строкой. В нашем примере мы заменяем все вхождения слова «грустный» на «плохой», используя`FindReplaceOptions` вариант с`FindReplaceDirection.Forward` направление поиска:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Шаг 4: Сохранение отредактированного документа

 Наконец, мы сохраняем измененный документ в указанный каталог, используя`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Пример исходного кода для замены строкой с использованием Aspose.Words для .NET

Вот полный образец исходного кода, иллюстрирующий использование замены строкой символов в Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Заменить строкой» Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы создать документ, вставить текст, заменить строку и сохранить измененный документ.
