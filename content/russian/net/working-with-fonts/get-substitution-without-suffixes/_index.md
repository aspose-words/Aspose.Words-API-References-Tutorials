---
title: Получить замену без суффиксов
linktitle: Получить замену без суффиксов
second_title: API обработки документов Aspose.Words
description: В этом руководстве вы узнаете, как получить переопределения без суффиксов в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/get-substitution-without-suffixes/
---

В этом уроке мы покажем вам, как получить переопределения без суффиксов в документе Word, используя библиотеку Aspose.Words для .NET. Замены без суффиксов используются для решения проблем замены шрифтов при отображении или печати документов. Мы шаг за шагом проведем вас, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предварительные условия
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Практическое знание языка программирования C#.
- Библиотека Aspose.Words для .NET, установленная в вашем проекте.

## Шаг 1. Определите каталог документов.
 Во-первых, вам нужно установить путь к каталогу, соответствующий местоположению вашего документа Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ и настройте замены без суффиксов.
 Далее мы загрузим документ, используя`Document` класс и настройте замены без суффиксов, используя`DocumentSubstitutionWarnings` сорт. Мы также добавим источник шрифтов, указав папку, содержащую шрифты.

```csharp
// Загрузите документ и настройте замены без суффиксов.
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## Шаг 3. Сохраните документ.
Наконец, мы сохраним документ с примененными переопределениями без суффиксов.

```csharp
// Сохраните документ
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### Пример исходного кода для получения замены без суффиксов с использованием Aspose.Words для .NET 
```csharp

//Путь к каталогу ваших документов
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
В этом уроке мы увидели, как получить переопределения без суффиксов в документе Word с помощью Aspose.Words для .NET. Замены без суффиксов полезны для решения проблем с заменой шрифтов. Не стесняйтесь использовать эту функцию, чтобы улучшить отображение и печать ваших документов.

### Часто задаваемые вопросы

#### Вопрос: Почему Aspose.Words добавляет суффиксы к замене шрифтов?

О: Aspose.Words добавляет суффиксы к заменам шрифтов, чтобы избежать конфликтов между исходными и замененными шрифтами. Это помогает обеспечить максимальную совместимость при преобразовании и работе с документами.

#### Вопрос: Как я могу получить замены шрифтов без суффиксов в Aspose.Words?

 О: Чтобы получить замены шрифтов без суффиксов в Aspose.Words, вы можете использовать команду`FontSubstitutionSettings` класс и`RemoveSuffixes` свойство. Установка этого свойства в`true` получит замены шрифтов без добавленных суффиксов.

#### Вопрос: Можно ли отключить добавление суффиксов к замене шрифтов в Aspose.Words?

О: Нет, отключить добавление суффиксов к замене шрифтов в Aspose.Words невозможно. Суффиксы добавляются по умолчанию, чтобы обеспечить совместимость и согласованность документа.

#### Вопрос: Как я могу отфильтровать нежелательные суффиксы при замене шрифтов в Aspose.Words?

 О: Чтобы отфильтровать нежелательные суффиксы при замене шрифтов в Aspose.Words, вы можете использовать методы обработки строк, например, использование`Replace` или`Substring` методы удаления определенных суффиксов, которые вы не хотите включать.