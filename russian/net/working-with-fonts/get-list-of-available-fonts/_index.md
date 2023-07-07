---
title: Получить список доступных шрифтов
linktitle: Получить список доступных шрифтов
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как получить список шрифтов, доступных в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/get-list-of-available-fonts/
---
В этом руководстве мы объясним, как получить список шрифтов, доступных в Aspose.Words для .NET. Список доступных шрифтов позволяет узнать, какие шрифты вы можете использовать в своих документах. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

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

## Шаг 2. Настройте источники шрифтов
 Далее мы создадим экземпляр`FontSettings` и получить существующие источники шрифтов, используя`GetFontsSources()` метод. Мы также добавим новый источник шрифта, указав папку, содержащую шрифты.

```csharp
// Настройка источников шрифтов
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Добавить новый источник шрифта
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Шаг 3: Получите список доступных шрифтов
 Теперь мы просмотрим доступные шрифты с помощью`GetAvailableFonts()` метод для первого обновленного источника шрифта.

```csharp
// Получить список доступных шрифтов
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Пример исходного кода для получения списка доступных шрифтов с использованием Aspose.Words для .NET 

```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Добавьте новый источник папки, который даст указание Aspose.Words искать шрифты в следующей папке.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Добавьте пользовательскую папку, содержащую наши шрифты, в список существующих источников шрифтов.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Заключение
В этом руководстве мы увидели, как получить список шрифтов, доступных в Aspose.Words для .NET. Это позволит вам узнать, какие шрифты вы можете использовать в своих документах. Не стесняйтесь использовать эту функцию, чтобы выбрать подходящие шрифты для ваших нужд.

### Часто задаваемые вопросы

#### Q: Как я могу получить список шрифтов, доступных в Aspose.Words?

 О: Чтобы получить список шрифтов, доступных в Aspose.Words, вы можете использовать`FontsProvider` класс и`GetAvailableFonts` метод. Этот метод вернет список всех шрифтов, установленных в вашей системе.

#### В: Могу ли я отфильтровать список доступных шрифтов по определенным критериям в Aspose.Words?

О: Да, вы можете фильтровать список шрифтов, доступных в Aspose.Words, по определенным критериям. Например, вы можете фильтровать шрифты по семейству, стилю или языку.

#### Q: Как я могу использовать список доступных шрифтов в своих документах Word?

 A: Чтобы использовать список шрифтов, доступных в ваших документах Word, вы можете просмотреть список и выбрать подходящие шрифты, используя методы и свойства`FontSettings` класс в Aspose.Words.