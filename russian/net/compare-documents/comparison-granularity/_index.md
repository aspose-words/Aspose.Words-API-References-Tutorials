---
title: Гранулярность сравнения
linktitle: Гранулярность сравнения
second_title: Справочник по API Aspose.Words для .NET
description: Изучите функцию детализации сравнения Aspose.Words для .NET, которая позволяет сравнивать документы посимвольно, сообщая о внесенных изменениях.
type: docs
weight: 10
url: /ru/net/compare-documents/comparison-granularity/
---
Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция Compare Granularity в Aspose.Words для .NET.

## Шаг 1: Введение

Функция сравнения гранулярности Aspose.Words для .NET позволяет сравнивать документы на уровне символов. Это означает, что каждый символ будет сравниваться, и об изменениях будет сообщено соответствующим образом.

## Шаг 2. Настройка среды

Прежде чем начать, вам необходимо настроить среду разработки для работы с Aspose.Words for .NET. Убедитесь, что у вас установлена библиотека Aspose.Words и есть подходящий проект C# для встраивания кода.

## Шаг 3: Добавьте необходимые сборки

Чтобы использовать функцию сравнения гранулярности Aspose.Words для .NET, вам необходимо добавить в проект необходимые сборки. Убедитесь, что в вашем проекте есть правильные ссылки на Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Шаг 4: Создание документов

На этом шаге мы создадим два документа, используя класс DocumentBuilder. Эти документы будут использованы для сравнения.

```csharp
// Создайте документ А.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Создать документ Б.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Шаг 5: Настройка параметров сравнения

На этом этапе мы настроим параметры сравнения, чтобы указать степень детализации сравнения. Здесь мы будем использовать детализацию на уровне символов.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Шаг 6: Сравнение документов

Теперь сравним документы с помощью метода Compare класса Document. Изменения будут сохранены в документе А.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

`Compare`метод сравнивает документ А с документом Б и сохраняет изменения в документе А. Вы можете указать имя автора и дату сравнения для справки.

## Заключение

В этой статье мы рассмотрели функцию сравнения гранулярности Aspose.Words для .NET. Эта функция позволяет сравнивать документы на уровне символов и сообщать об изменениях. Вы можете использовать эти знания для выполнения подробных сравнений документов в своих проектах.

### Пример исходного кода для гранулярности сравнения с использованием Aspose.Words для .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```
