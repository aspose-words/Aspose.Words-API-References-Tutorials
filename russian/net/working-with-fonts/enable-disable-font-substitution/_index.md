---
title: Включить Отключить замену шрифта
linktitle: Включить Отключить замену шрифта
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как включить или отключить подстановку шрифтов в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/enable-disable-font-substitution/
---
В этом руководстве мы расскажем, как включить или отключить подстановку шрифтов в документе Word при его рендеринге с использованием библиотеки Aspose.Words для .NET. Включение или отключение замены шрифтов позволяет управлять автоматической заменой отсутствующих шрифтов шрифтом по умолчанию. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте
- Документ Word, который вы хотите отобразить с заменой шрифта или без нее

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Загрузите документ и настройте параметры шрифта.
 Затем мы загрузим документ Word, который вы хотите отобразить, и создадим экземпляр`FontSettings` класс для обработки настроек шрифта. Мы установим переопределение шрифта по умолчанию, указав имя шрифта в`DefaultFontName` и отключить переопределение информации о шрифте с помощью`Enabled` установлен в`false`.

```csharp
//Загрузите документ
Document doc = new Document(dataDir + "Rendering.docx");

// Настройте параметры шрифта
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

// Применение настроек шрифта к документу
doc.FontSettings = fontSettings;
```

## Шаг 3: Сохраните визуализированный документ
Наконец, мы сохраним визуализированный документ, в котором будут соблюдаться определенные параметры переопределения шрифта.

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### Пример исходного кода для включения отключения замены шрифта с помощью Aspose.Words для .NET 

```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## Заключение
В этом руководстве мы увидели, как включить или отключить замену шрифта в документе Word при его рендеринге с помощью Aspose.Words для .NET. Управляя заменой шрифтов, вы можете влиять на то, как отсутствующие шрифты обрабатываются в визуализированных документах. Не стесняйтесь использовать эту функцию для настройки управления шрифтами в документах Word.