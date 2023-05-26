---
title: Получить замену без суффиксов
linktitle: Получить замену без суффиксов
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как получить переопределения без суффиксов в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/get-substitution-without-suffixes/
---

В этом руководстве мы покажем вам, как получить переопределения без суффиксов в документе Word с помощью библиотеки Aspose.Words для .NET. Подстановки без суффиксов используются для решения проблем с заменой шрифтов при отображении или печати документов. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ и настройте замены без суффиксов.
 Далее мы загрузим документ с помощью`Document` класс и настроить безсуффиксные замены с помощью`DocumentSubstitutionWarnings` сорт. Мы также добавим источник шрифта, указав папку, содержащую шрифты.

```csharp
//Загрузите документ и настройте замены без суффиксов
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Шаг 3: Сохраните документ
Наконец, мы сохраним документ с примененными переопределениями без суффиксов.

```csharp
// Сохраните документ
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Пример исходного кода для получения замены без суффиксов с использованием Aspose.Words для .NET 
```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## Заключение
В этом руководстве мы увидели, как получить переопределения без суффиксов в документе Word с помощью Aspose.Words для .NET. Замены без суффиксов полезны для решения проблем с заменой шрифтов. Не стесняйтесь использовать эту функцию для улучшения отображения и печати ваших документов.
