---
title: Включить Отключить замену шрифтов
linktitle: Включить Отключить замену шрифтов
second_title: API обработки документов Aspose.Words
description: Узнайте, как включить или отключить замену шрифтов в документах Word с помощью Aspose.Words для .NET. Убедитесь, что ваши документы выглядят одинаково на всех платформах.
type: docs
weight: 10
url: /ru/net/working-with-fonts/enable-disable-font-substitution/
---
## Введение

Вы когда-нибудь оказывались в ситуации, когда тщательно выбранные вами шрифты в документе Word заменяются при просмотре на другом компьютере? Раздражает, правда? Это происходит из-за подмены шрифта — процесса, при котором система заменяет отсутствующий шрифт доступным. Но не волнуйтесь! С помощью Aspose.Words для .NET вы можете легко управлять заменой шрифтов и контролировать ее. В этом уроке мы покажем вам, как включить или отключить замену шрифтов в документах Word, чтобы ваши документы всегда выглядели так, как вы хотите.

## Предварительные условия

Прежде чем углубляться в пошаговые инструкции, давайте убедимся, что у вас есть все необходимое:

-  Aspose.Words для .NET: загрузите последнюю версию[здесь](https://releases.aspose.com/words/net/).
- Visual Studio: любая версия, поддерживающая .NET.
- Базовые знания C#: это поможет вам следовать примерам кодирования.

## Импортировать пространства имен

Для начала убедитесь, что в ваш проект импортированы необходимые пространства имен. Добавьте их в начало вашего файла C#:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Теперь давайте разобьем процесс на простые и выполнимые шаги.

## Шаг 1. Настройте свой проект

Сначала настройте новый проект в Visual Studio и добавьте ссылку на библиотеку Aspose.Words для .NET. Если вы еще этого не сделали, загрузите его с сайта[Веб-сайт Aspose](https://releases.aspose.com/words/net/).

## Шаг 2. Загрузите документ

Затем загрузите документ, с которым хотите работать. Вот как это сделать:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа. Этот код загружает документ в память, чтобы вы могли манипулировать им.

## Шаг 3. Настройте параметры шрифта

 Теперь давайте создадим`FontSettings` объект для управления настройками подстановки шрифтов:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Шаг 4. Установите замену шрифта по умолчанию

Установите замену шрифта по умолчанию на шрифт по вашему выбору. Этот шрифт будет использоваться, если исходный шрифт недоступен:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

В этом примере мы используем Arial в качестве шрифта по умолчанию.

## Шаг 5. Отключите подмену информации о шрифте

Чтобы отключить подмену информации о шрифтах, которая не позволяет системе заменять отсутствующие шрифты доступными, используйте следующий код:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Шаг 6. Примените настройки шрифта к документу

Теперь примените эти настройки к вашему документу:

```csharp
doc.FontSettings = fontSettings;
```

## Шаг 7. Сохраните документ

Наконец, сохраните измененный документ. Вы можете сохранить его в любом формате, который вам нравится. Для этого урока мы сохраним его в формате PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Заключение

И вот оно! Следуя этим шагам, вы сможете легко управлять заменой шрифтов в документах Word с помощью Aspose.Words для .NET. Это гарантирует, что ваши документы сохранят свой предполагаемый внешний вид, независимо от того, где их просматривают.

## Часто задаваемые вопросы

### Могу ли я использовать для замены шрифты, отличные от Arial?

 Абсолютно! Вы можете указать любой шрифт, доступный в вашей системе, изменив имя шрифта в`DefaultFontName` свойство.

### Что произойдет, если указанный шрифт по умолчанию недоступен?

Если шрифт по умолчанию недоступен, Aspose.Words будет использовать системный резервный механизм для поиска подходящей замены.

### Могу ли я снова включить подмену шрифтов после ее отключения?

 Да, вы можете переключить`Enabled` собственность`FontInfoSubstitution` вернуться к`true` если вы хотите снова включить подмену шрифтов.

### Есть ли способ проверить, какие шрифты заменяются?

Да, Aspose.Words предоставляет методы для регистрации и отслеживания замены шрифтов, позволяя вам видеть, какие шрифты заменяются.

### Могу ли я использовать этот метод для других форматов документов, кроме DOCX?

Определенно! Aspose.Words поддерживает различные форматы, и вы можете применить эти настройки шрифта к любому поддерживаемому формату.