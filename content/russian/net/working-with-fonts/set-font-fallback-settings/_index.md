---
title: Установить настройки резервного шрифта
linktitle: Установить настройки резервного шрифта
second_title: API обработки документов Aspose.Words
description: Узнайте, как настроить параметры резервного шрифта в Aspose.Words для .NET. Это подробное руководство гарантирует правильное отображение всех символов в ваших документах.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-font-fallback-settings/
---
## Введение

При работе с документами, содержащими разнообразные текстовые элементы, например, написанные на разных языках или специальные символы, очень важно убедиться, что эти элементы отображаются правильно. Aspose.Words для .NET предлагает мощную функцию под названием «Настройки резервного шрифта», которая помогает определить правила замены шрифтов, когда исходный шрифт не поддерживает определенные символы. В этом руководстве мы рассмотрим, как настроить параметры резервного шрифта с помощью Aspose.Words для .NET, в пошаговом руководстве.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания C#: Знакомство с языком программирования C# и платформой .NET.
-  Aspose.Words для .NET: загрузите и установите с[ссылка для скачивания](https://releases.aspose.com/words/net/).
- Среда разработки: установка, подобная Visual Studio, для написания и запуска вашего кода.
-  Образец документа: Имейте образец документа (например,`Rendering.docx`) готов к тестированию.
- XML правил возврата шрифтов: подготовьте XML-файл, определяющий правила возврата шрифтов.

## Импортировать пространства имен

Чтобы использовать Aspose.Words, вам необходимо импортировать необходимые пространства имен. Это обеспечивает доступ к различным классам и методам, необходимым для обработки документов.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
using System;
```

## Шаг 1. Определите каталог документов

Сначала определите каталог, в котором хранится ваш документ. Это необходимо для поиска и обработки вашего документа.

```csharp
// Путь к каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ

 Загрузите свой документ в Aspose.Words.`Document` объект. Этот шаг позволяет работать с документом программно.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3. Настройте параметры шрифта

 Создать новый`FontSettings` объект и загрузите настройки резервного шрифта из XML-файла. Этот XML-файл содержит правила для резервного шрифта.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
```

## Шаг 4. Примените настройки шрифта к документу

 Назначьте настроенное`FontSettings`к документу. Это гарантирует, что правила возврата шрифтов будут применены при рендеринге документа.

```csharp
doc.FontSettings = fontSettings;
```

## Шаг 5: Сохраните документ

Наконец, сохраните документ. Настройки резервного шрифта будут использоваться во время операции сохранения, чтобы обеспечить правильную замену шрифта.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## XML-файл: правила возврата шрифтов

Вот пример того, как должен выглядеть ваш XML-файл, определяющий правила возврата шрифтов:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<FontFallbackSettings xmlns="Aspose.Words">
    <FallbackTable>
        <Rule Ranges="0B80-0BFF" FallbackFonts="Vijaya"/>
        <Rule Ranges="1F300-1F64F" FallbackFonts="Segoe UI Emoji, Segoe UI Symbol"/>
        <Rule Ranges="2000-206F, 2070-209F, 20B9" FallbackFonts="Arial" />
        <Rule Ranges="3040-309F" FallbackFonts="MS Gothic" BaseFonts="Times New Roman"/>
        <Rule Ranges="3040-309F" FallbackFonts="MS Mincho"/>
        <Rule FallbackFonts="Arial Unicode MS"/>
    </FallbackTable>
</FontFallbackSettings>
```

## Заключение

Выполнив эти шаги, вы сможете эффективно настроить и использовать настройки резервного шрифта в Aspose.Words для .NET. Это гарантирует, что в ваших документах все символы будут отображаться правильно, даже если исходный шрифт не поддерживает определенные символы. Реализация этих настроек значительно повысит качество и читаемость ваших документов.

## Часто задаваемые вопросы

### Вопрос 1. Что такое резервный шрифт?

Резервный шрифт — это функция, которая позволяет заменять шрифты, когда исходный шрифт не поддерживает определенные символы, обеспечивая правильное отображение всех текстовых элементов.

### Вопрос 2. Могу ли я указать несколько резервных шрифтов?

Да, вы можете указать несколько резервных шрифтов в правилах XML. Aspose.Words будет проверять каждый шрифт в указанном порядке, пока не найдет тот, который поддерживает этот символ.

### Вопрос 3: Где я могу скачать Aspose.Words для .NET?

 Вы можете скачать его с сайта[Страница загрузки Aspose](https://releases.aspose.com/words/net/).

### Вопрос 4. Как создать XML-файл для правил резервного использования шрифтов?

XML-файл можно создать с помощью любого текстового редактора. Он должен соответствовать структуре, показанной в примере, приведенном в этом руководстве.

### Вопрос 5: Доступна ли поддержка Aspose.Words?

 Да, вы можете найти поддержку на[Форум поддержки Aspose.Words](https://forum.aspose.com/c/words/8).