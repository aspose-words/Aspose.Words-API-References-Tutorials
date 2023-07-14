---
title: Настройки шрифта Экземпляр по умолчанию
linktitle: Настройки шрифта Экземпляр по умолчанию
second_title: API обработки документов Aspose.Words
description: В этом руководстве вы узнаете, как настроить параметры шрифта по умолчанию в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/font-settings-default-instance/
---

В этом руководстве мы расскажем, как настроить параметры шрифта по умолчанию в документе Word с помощью библиотеки Aspose.Words для .NET. Настройки шрифта по умолчанию позволяют указать источники шрифтов, используемые при загрузке и отображении документов. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

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

## Шаг 2. Настройте параметры шрифта по умолчанию
 Далее мы создадим экземпляр`FontSettings` с использованием`FontSettings.DefaultInstance`, а затем мы укажем источники шрифтов, используемые при загрузке и отображении документов. В этом примере мы используем источник системного шрифта и источник шрифта папки.

```csharp
// Настройте параметры шрифта по умолчанию
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Шаг 3. Загрузите документ с настройками шрифта.
 Теперь мы загрузим документ, используя`LoadOptions` и указание настроек шрифта для использования.

```csharp
// Загрузите документ с настройками шрифта
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Пример исходного кода для экземпляра настроек шрифта по умолчанию с использованием Aspose.Words для .NET 
```csharp

//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Заключение
В этом руководстве мы увидели, как настроить параметры шрифта по умолчанию в документе Word с помощью Aspose.Words для .NET. Указав источники шрифтов, используемые при загрузке и отображении документов, вы можете контролировать внешний вид шрифтов в ваших документах. Не стесняйтесь использовать эту функцию для настройки параметров шрифта в ваших проектах.

### Часто задаваемые вопросы

#### Q: Как я могу установить шрифт по умолчанию в Aspose.Words?

 О: Чтобы установить шрифт по умолчанию в Aspose.Words, вы можете использовать`FontSettings` класс и`DefaultFontName` свойство, указывающее имя желаемого шрифта.

#### В: Могу ли я указать размер шрифта по умолчанию в Aspose.Words?

 О: Да, вы можете указать размер шрифта по умолчанию в Aspose.Words с помощью`DefaultFontSize`собственность`FontSettings` сорт. Вы можете установить желаемый размер точки.

#### В: Можно ли установить цвет шрифта по умолчанию в Aspose.Words?

 О: Да, вы можете установить цвет шрифта по умолчанию в Aspose.Words с помощью`DefaultColor`собственность`FontSettings` сорт. Вы можете указать цвет, используя значения RGB или предопределенные имена.

#### Вопрос. Применяются ли настройки шрифта по умолчанию ко всем документам?

О: Да, настройки шрифта по умолчанию применяются ко всем документам, созданным или отредактированным в Aspose.Words, если для отдельного документа не заданы особые настройки.