---
title: Word заменить текст, содержащий метасимволы
linktitle: Word заменить текст, содержащий метасимволы
second_title: API обработки документов Aspose.Words
description: Узнайте, как заменить текст, содержащий метасимволы, в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/replace-text-containing-meta-characters/
---
В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию Word Replace Text Containing Meta Characters в библиотеке Aspose.Words для .NET. Эта функция позволяет заменять части текста в документе, содержащие определенные метасимволы.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Создание нового документа

 Прежде чем мы начнем использовать замену текста метасимволами, нам нужно создать новый документ, используя Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` объект:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Шаг 2. Вставьте текст в документ

 Когда у нас есть документ, мы можем вставить текст, используя`DocumentBuilder` объект. В нашем примере мы используем`Writeln` способ вставки нескольких абзацев текста в разные разделы:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## Шаг 3. Настройка параметров поиска и замены

 Теперь мы настроим параметры поиска и замены, используя`FindReplaceOptions` объект. В нашем примере мы устанавливаем выравнивание замененных абзацев на «По центру»:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## Шаг 4: Замена текста, содержащего метасимволы

 Мы используем`Range.Replace`метод для замены текста, содержащего метасимволы. В нашем примере мы заменяем каждое вхождение слова «раздел», за которым следует разрыв абзаца, на то же слово, за которым следуют несколько дефисов и новый разрыв абзаца:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Шаг 5. Замена пользовательского текстового тега

 Мы также используем`Range.Replace` метод замены пользовательского "{insert-section}" текстовый тег с разрывом раздела. В нашем примере мы заменяем "{insert-section}" с "&b", чтобы вставить разрыв раздела:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Шаг 6: Сохранение отредактированного документа

 Наконец, мы сохраняем измененный документ в указанный каталог, используя`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Пример исходного кода для замены текста, содержащего метасимволы, с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий использование замены текста, содержащего метасимволы, с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// Удвойте каждый разрыв абзаца после слова «раздел», добавьте подчеркивание и сделайте его по центру.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Вставьте разрыв раздела вместо пользовательского текстового тега.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Заменить текст, содержащий метасимволы» в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы создать документ, вставить текст, заменить текст, содержащий метасимволы, и сохранить измененный документ.

### Часто задаваемые вопросы

#### В: Что такое функция «Заменить текст, содержащий метасимволы» в Aspose.Words для .NET?

О: Функция «Заменить текст, содержащий метасимволы» в Aspose.Words для .NET позволяет заменять части текста в документе, содержащие определенные метасимволы. Вы можете использовать эту функцию для выполнения расширенных замен в документе с учетом метасимволов.

#### В: Как создать новый документ в Aspose.Words для .NET?

 О: Прежде чем использовать функцию «Заменить текст, содержащий метасимволы», вы должны создать новый документ, используя Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` объект. Вот пример кода для создания нового документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### В: Как вставить текст в документ с помощью Aspose.Words для .NET?

 A: Когда у вас есть документ, вы можете вставить текст, используя`DocumentBuilder` объект. В нашем примере мы используем`Writeln` способ вставки нескольких абзацев текста в разные разделы:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### В: Как настроить параметры поиска и замены в Aspose.Words для .NET?

 A: Теперь мы настроим параметры поиска и замены, используя`FindReplaceOptions` объект. В нашем примере мы устанавливаем выравнивание замененных абзацев на «По центру»:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### В: Как заменить текст, содержащий метасимволы, в документе с помощью Aspose.Words для .NET?

 О: Мы используем`Range.Replace` метод для замены текста, содержащего метасимволы. В нашем примере мы заменяем каждое вхождение слова «раздел», за которым следует разрыв абзаца, на то же слово, за которым следуют несколько дефисов и новый разрыв абзаца:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### В: Как заменить пользовательский текстовый тег, содержащий метасимволы, в документе с помощью Aspose.Words для .NET?

 О: Мы также используем`Range.Replace` метод замены пользовательского "{insert-section}" текстовый тег с разрывом раздела. В нашем примере мы заменяем "{insert-section}" с "&b", чтобы вставить разрыв раздела:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### В: Как сохранить отредактированный документ в Aspose.Words для .NET?

 О: После того, как вы внесли изменения в документ, вы можете сохранить его в указанном каталоге с помощью`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```