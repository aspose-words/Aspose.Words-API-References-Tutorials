---
title: Получить список доступных шрифтов
linktitle: Получить список доступных шрифтов
second_title: API обработки документов Aspose.Words
description: В этом уроке вы узнаете, как получить список шрифтов, доступных в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/get-list-of-available-fonts/
---
В этом уроке мы объясним, как получить список шрифтов, доступных в Aspose.Words для .NET. Список доступных шрифтов позволяет узнать, какие шрифты можно использовать в своих документах. Мы шаг за шагом проведем вас, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

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

## Шаг 2. Настройте источники шрифтов
 Далее мы создадим экземпляр`FontSettings` и получите существующие источники шрифтов, используя`GetFontsSources()` метод. Мы также добавим новый источник шрифтов, указав папку, содержащую шрифты.

```csharp
// Настройка источников шрифтов
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Добавить новый источник шрифта
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Шаг 3. Получите список доступных шрифтов.
 Теперь мы просмотрим доступные шрифты, используя`GetAvailableFonts()` метод для первого обновленного источника шрифта.

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


### Пример исходного кода для получения списка доступных шрифтов с помощью Aspose.Words для .NET 

```csharp

// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Добавьте новый источник папки, который будет указывать Aspose.Words искать шрифты в следующей папке.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
//Добавьте пользовательскую папку, содержащую наши шрифты, в список существующих источников шрифтов.
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
В этом уроке мы увидели, как получить список шрифтов, доступных в Aspose.Words для .NET. Это позволит вам узнать, какие шрифты вы можете использовать в своих документах. Не стесняйтесь использовать эту функцию, чтобы выбрать шрифты, соответствующие вашим потребностям.

### Часто задаваемые вопросы

#### Вопрос: Как получить список шрифтов, доступных в Aspose.Words?

 О: Чтобы получить список шрифтов, доступных в Aspose.Words, вы можете использовать команду`FontsProvider` класс и`GetAvailableFonts` метод. Этот метод вернет список всех шрифтов, установленных в вашей системе.

#### Вопрос: Могу ли я отфильтровать список доступных шрифтов по определенным критериям в Aspose.Words?

О: Да, вы можете фильтровать список шрифтов, доступных в Aspose.Words, используя определенные критерии. Например, вы можете фильтровать шрифты по семейству, стилю или языку.

#### Вопрос: Как я могу использовать список доступных шрифтов в своих документах Word?

О: Чтобы использовать список шрифтов, доступных в ваших документах Word, вы можете просмотреть список и выбрать подходящие шрифты, используя методы и свойства`FontSettings` класс в Aspose.Words.