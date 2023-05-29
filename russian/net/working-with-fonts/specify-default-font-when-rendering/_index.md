---
title: Укажите шрифт по умолчанию при рендеринге
linktitle: Укажите шрифт по умолчанию при рендеринге
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по указанию шрифта по умолчанию при отображении документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/specify-default-font-when-rendering/
---

В этом руководстве мы пошагово проведем вас через процесс указания шрифта по умолчанию при отображении документа с использованием Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. К концу этого руководства вы будете знать, как указать шрифт по умолчанию для использования при отображении ваших документов с помощью Aspose.Words для .NET.

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где вы хотите сохранить отредактированный визуализированный документ. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите документ для рендеринга
 Затем вам нужно загрузить документ для рендеринга с помощью`Document` сорт. Обязательно укажите правильный путь к документу.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3: Установите шрифт по умолчанию
 Теперь вы можете указать шрифт по умолчанию для использования при рендеринге, создав экземпляр`FontSettings` класс и установка`DefaultFontName` собственность`DefaultFontSubstitution` возражать против`DefaultFontSubstitution` объект`SubstitutionSettings` из`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Шаг 4: Сохраните визуализированный документ
 Наконец, вы можете сохранить визуализированный документ в файл, используя`Save()` метод`Document` сорт. Обязательно укажите правильный путь и имя файла.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Пример исходного кода для указания шрифта по умолчанию при рендеринге с использованием Aspose.Words для .NET 

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Если заданный здесь шрифт по умолчанию не может быть найден во время рендеринга, тогда
// вместо этого используется ближайший шрифт на машине.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Заключение
В этом руководстве мы узнали, как указать шрифт по умолчанию при рендеринге документа с использованием Aspose.Words для .NET. Следуя этому пошаговому руководству, вы можете легко установить шрифт по умолчанию для использования при рендеринге ваших документов. Aspose.Words предлагает мощный и гибкий API для работы со шрифтами в ваших документах. Обладая этими знаниями, вы можете контролировать и настраивать визуализацию ваших документов в соответствии с вашими конкретными потребностями.