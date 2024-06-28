---
title: Слово заменить текст, содержащий метасимволы
linktitle: Слово заменить текст, содержащий метасимволы
second_title: API обработки документов Aspose.Words
description: Узнайте, как заменить текст, содержащий метасимволы, в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/replace-text-containing-meta-characters/
---
В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию замены текста, содержащего метасимволы Word, в библиотеке Aspose.Words для .NET. Эта функция позволяет заменять в документе части текста, содержащие определенные метасимволы.

## Предварительные условия

- Базовые знания языка C#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1. Создайте новый документ

 Прежде чем мы начнем использовать замену текста метасимволов, нам нужно создать новый документ, используя Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` объект:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Шаг 2. Вставьте текст в документ.

 Когда у нас есть документ, мы можем вставить текст, используя`DocumentBuilder` Объект Object. В нашем примере мы используем`Writeln` метод для вставки нескольких абзацев текста в разные разделы:

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

 Теперь мы настроим параметры поиска и замены, используя`FindReplaceOptions` Объект Object. В нашем примере мы установили выравнивание заменяемых абзацев на «По центру»:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## Шаг 4. Замена текста, содержащего метасимволы

 Мы используем`Range.Replace`метод для выполнения замены текста, содержащего метасимволы. В нашем примере мы заменяем каждое появление слова «раздел», за которым следует разрыв абзаца, тем же словом, за которым следуют несколько тире и новый разрыв абзаца:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Шаг 5. Замена пользовательского текстового тега

 Мы также используем`Range.Replace` метод замены пользовательского "{insert-section}"текстовый тег с разрывом раздела. В нашем примере заменяем"{insert-section}" с "&b", чтобы вставить разрыв раздела:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Шаг 6: Сохраните отредактированный документ

Наконец, мы сохраняем измененный документ в указанном каталоге, используя команду`Save` метод:

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

	// Удвойте разрыв каждого абзаца после слова «раздел», добавьте подчеркивание и расположите его по центру.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Вставьте разрыв раздела вместо пользовательского текстового тега.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию замены текста, содержащего метасимволы, в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы создать документ, вставить текст, заменить текстовые метасимволы и сохранить измененный документ.

### Часто задаваемые вопросы

#### Вопрос: Что такое функция «Заменить текст, содержащий метасимволы» в Aspose.Words для .NET?

О: Функция «Заменить текст, содержащий метасимволы» в Aspose.Words for .NET позволяет заменять части текста в документе, содержащие определенные метасимволы. Вы можете использовать эту функцию для выполнения расширенных замен в документе с учетом метасимволов.

#### Вопрос: Как создать новый документ в Aspose.Words для .NET?

 О: Прежде чем использовать функцию «Заменить текст, содержащий метасимволы», вы должны создать новый документ с помощью Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` Объект Object. Вот пример кода для создания нового документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Вопрос: Как вставить текст в документ с помощью Aspose.Words for .NET?

 О: Если у вас есть документ, вы можете вставить текст с помощью`DocumentBuilder` Объект Object. В нашем примере мы используем`Writeln` метод для вставки нескольких абзацев текста в разные разделы:

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

#### Вопрос: Как настроить параметры поиска и замены в Aspose.Words для .NET?

 О: Теперь мы настроим параметры поиска и замены, используя`FindReplaceOptions` Объект Object. В нашем примере мы установили выравнивание заменяемых абзацев на «По центру»:

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### Вопрос: Как заменить текст, содержащий метасимволы, в документе с помощью Aspose.Words for .NET?

 О: Мы используем`Range.Replace` метод для выполнения замены текста, содержащего метасимволы. В нашем примере мы заменяем каждое появление слова «раздел», за которым следует разрыв абзаца, тем же словом, за которым следуют несколько тире и новый разрыв абзаца:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### Вопрос: Как заменить в документе пользовательский текстовый тег, содержащий метасимволы, с помощью Aspose.Words for .NET?

 О: Мы также используем`Range.Replace` метод замены пользовательского "{insert-section}"текстовый тег с разрывом раздела. В нашем примере заменяем"{insert-section}" с "&b", чтобы вставить разрыв раздела:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### Вопрос: Как сохранить отредактированный документ в Aspose.Words for .NET?

 О: После внесения изменений в документ вы можете сохранить его в указанный каталог, используя команду`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```