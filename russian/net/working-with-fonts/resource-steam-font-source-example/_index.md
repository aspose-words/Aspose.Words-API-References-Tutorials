---
title: Пример исходного кода шрифта Steam
linktitle: Пример исходного кода шрифта Steam
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать источник шрифтов Resource Stream для загрузки пользовательских шрифтов в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/resource-steam-font-source-example/
---

В этом руководстве мы расскажем, как использовать источник шрифтов Resource Flow с Aspose.Words для .NET. Этот источник шрифтов позволяет вам загружать шрифты из потока ресурсов, что может быть полезно, если вы хотите включить пользовательские шрифты в свое приложение.

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

## Шаг 2. Загрузите документ и установите источник шрифта Resource Stream
 Далее мы загрузим документ с помощью`Document` class и установите источник шрифта потока ресурсов, используя`FontSettings.DefaultInstance.SetFontsSources()` сорт. Это позволит Aspose.Words найти шрифты в потоке ресурсов.

```csharp
// Загрузите документ и установите источник шрифта потока ресурсов
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## Шаг 3: Сохраните документ
Наконец, мы сохраним документ. Шрифты будут загружены из указанного потока ресурсов и встроены в документ.

```csharp
// Сохраните документ
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### Пример исходного кода для примера источника шрифта Resource Steam с использованием Aspose.Words для .NET 

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## Заключение
Из этого руководства вы узнали, как использовать источник шрифтов Resource Flow с Aspose.Words для .NET. Эта функция позволяет загружать шрифты из канала ресурсов, что полезно, если вы хотите встроить пользовательские шрифты в свои документы. Поэкспериментируйте с различными шрифтами и изучите возможности Aspose.Words для управления шрифтами.
