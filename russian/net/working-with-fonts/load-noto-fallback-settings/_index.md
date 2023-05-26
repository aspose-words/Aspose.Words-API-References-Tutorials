---
title: Загрузить резервные настройки Noto
linktitle: Загрузить резервные настройки Noto
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как загрузить параметры переопределения Noto в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/load-noto-fallback-settings/
---
В этом руководстве мы расскажем, как загрузить настройки замены шрифта Noto в документ Word с помощью библиотеки Aspose.Words для .NET. Настройки Noto Font Substitution позволяют управлять заменой шрифтов при отображении или печати документов. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

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

## Шаг 2. Загрузите документ и настройте параметры замены шрифта.
 Далее мы загрузим документ с помощью`Document` класс и настройте параметры переопределения шрифта с помощью`FontSettings` сорт. Мы загрузим резервные настройки шрифта Noto, используя`LoadNotoFallbackSettings()` метод.

```csharp
// Загрузите документ и настройте параметры замены шрифта
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
```

## Шаг 3: Сохраните документ
Наконец, мы сохраним документ с примененными настройками замены шрифта Noto.

```csharp
// Сохраните документ
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");
```


### Пример исходного кода для резервных настроек Noto с использованием Aspose.Words для .NET 
```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.LoadNotoFallbackSettings();
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.NotoFallbackSettings.pdf");

```

## Заключение
В этом руководстве мы увидели, как загрузить настройки замены шрифта Noto в документ Word с помощью Aspose.Words для .NET. Настройки замены шрифтов Noto позволяют управлять заменой шрифтов для улучшения отображения и печати ваших документов. Не стесняйтесь использовать эту функцию, чтобы настроить замену шрифта в соответствии с вашими потребностями.