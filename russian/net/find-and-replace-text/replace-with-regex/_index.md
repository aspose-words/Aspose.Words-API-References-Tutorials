---
title: Заменить регулярным выражением
linktitle: Заменить регулярным выражением
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как выполнять замену текста на основе регулярных выражений в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/find-and-replace-text/replace-with-regex/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Заменить на регулярное выражение» в библиотеке Aspose.Words для .NET. Эта функция позволяет выполнять замену текста на основе определенных шаблонов, определяемых регулярным выражением.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Создание нового документа

 Прежде чем мы начнем использовать замену регулярных выражений, нам нужно создать новый документ, используя Aspose.Words для .NET. Это можно сделать, создав экземпляр`Document` объект:

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

## Шаг 3. Настройка параметров поиска и замены

 Теперь мы настроим параметры поиска и замены, используя`FindReplaceOptions` объект. В нашем примере мы используем параметры по умолчанию:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## Шаг 4: Замените регулярным выражением

 Мы используем`Range.Replace` метод для замены текста с помощью регулярного выражения. В нашем примере мы используем регулярное выражение "[с|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Шаг 5: Сохранение измененного документа

 Наконец, мы сохраняем измененный документ в указанный каталог, используя`Save` метод:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Пример исходного кода для замены регулярным выражением с использованием Aspose.Words для .NET

Вот полный образец исходного кода, демонстрирующий использование замены регулярных выражений с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Заменить регулярным выражением» Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы создать документ, вставить текст, выполнить замену регулярным выражением и сохранить измененный документ.
