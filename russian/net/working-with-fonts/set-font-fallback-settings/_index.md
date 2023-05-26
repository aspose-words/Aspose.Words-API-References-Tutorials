---
title: Установить параметры резервного шрифта
linktitle: Установить параметры резервного шрифта
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как установить параметры замены шрифта в Aspose.Words для .NET и настроить замену шрифта в ваших документах Word.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-font-fallback-settings/
---
В этом руководстве мы покажем вам, как установить параметры замены шрифта в документе Word с помощью Aspose.Words для .NET. Параметры замены шрифтов позволяют указать шрифты для замены, которые будут использоваться, когда указанные шрифты недоступны.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Определите каталог документов
Начните с установки пути к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузите настройки замены шрифта
 Создайте экземпляр`FontSettings` класс и использовать`Load`метод для загрузки настроек переопределения шрифта из XML-файла. Указанный файл XML должен содержать используемые правила замены шрифта.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## Шаг 3: Примените настройки замены шрифта
 Свяжите параметры замены шрифта с документом, назначив их`FontSettings` свойство.

```csharp
doc.FontSettings = fontSettings;
```

## Шаг 4: Сохраните документ
 Сохраните документ с помощью`Save` метод`Document` с соответствующим путем и именем файла.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### Пример исходного кода для установки параметров резервного шрифта с использованием Aspose.Words для .NET 
```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## Заключение
В этом руководстве вы узнали, как установить параметры замены шрифта в документе Word с помощью Aspose.Words для .NET. Поэкспериментируйте с различными правилами замены шрифтов, чтобы убедиться, что ваш документ выглядит согласованно, даже если указанные шрифты недоступны.
