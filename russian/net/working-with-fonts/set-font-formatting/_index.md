---
title: Установить форматирование шрифта
linktitle: Установить форматирование шрифта
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как настроить форматирование шрифта в документе Word с помощью Aspose.Words для .NET и создавать привлекательные документы.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-font-formatting/
---
В этом руководстве мы покажем вам, как настроить форматирование шрифта в документе Word с помощью Aspose.Words для .NET. Вы узнаете, как применять такие стили, как жирный шрифт, цвет, курсив, шрифт, размер, интервал и подчеркивание.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Определите каталог документов
Начните с установки пути к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создайте и отформатируйте документ
 Создайте экземпляр`Document` класс и`DocumentBuilder` класс для создания документа. Использовать`Font` собственность`DocumentBuilder` для доступа к свойствам форматирования шрифта.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## Шаг 3: Сохраните документ
 Использовать`Save` метод сохранения документа с примененным форматированием шрифта. Заменять`"WorkingWithFonts.SetFontFormatting.docx"` с желаемым именем файла.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### Пример исходного кода для установки форматирования шрифта с использованием Aspose.Words для .NET 
```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## Заключение
Поздравляем! Теперь вы знаете, как настроить форматирование шрифта в документе Word с помощью Aspose.Words для .NET. Вы можете изучить дополнительные параметры форматирования шрифтов и создавать персонализированные и привлекательные документы Word.
