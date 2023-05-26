---
title: Установить папку со шрифтами
linktitle: Установить папку со шрифтами
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить каталог шрифтов в Aspose.Words для .NET и обеспечить доступность шрифтов, используемых в ваших документах.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-fonts-folder/
---
В этом уроке мы покажем вам, как установить каталог шрифтов в Aspose.Words для .NET. Вы узнаете, как указать каталог, содержащий шрифты, используемые в вашем документе Word.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Определите каталог документов
Начните с установки пути к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Установите каталог шрифтов
 Создайте экземпляр`FontSettings` класс и использовать`SetFontsFolder` метод, чтобы указать каталог, содержащий шрифты. Заменять`"Fonts"` с именем фактического каталога шрифтов.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Шаг 3: Загрузите документ с настройками шрифта
 Использовать`LoadOptions` класс, чтобы указать настройки шрифта в`FontSettings` вариант. Затем используйте`Document` class для загрузки документа с использованием этих параметров.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Пример исходного кода для установки папки шрифтов с использованием Aspose.Words для .NET 

```csharp

// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Заключение
Поздравляем! Теперь вы знаете, как установить каталог шрифтов в Aspose.Words для .NET. Вы можете использовать эту функцию, чтобы обеспечить доступность шрифтов, используемых в вашем документе, и обеспечить согласованность отображения шрифтов.
