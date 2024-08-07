---
title: Экспортировать поле формы ввода текста как текст
linktitle: Экспортировать поле формы ввода текста как текст
second_title: API обработки документов Aspose.Words
description: Узнайте, как экспортировать поля формы текстового ввода в виде обычного текста с помощью Aspose.Words for .NET, с помощью этого подробного пошагового руководства.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## Введение

Итак, вы погружаетесь в мир Aspose.Words для .NET? Потрясающий выбор! Если вы хотите узнать, как экспортировать поле формы ввода текста в виде текста, вы попали по адресу. Независимо от того, начинаете ли вы или совершенствуете свои навыки, это руководство проведет вас через все, что вам нужно знать. Давай начнем, ладно?

## Предварительные условия

Прежде чем мы углубимся в подробности, давайте убедимся, что у вас есть все необходимое для бесперебойной работы:

-  Aspose.Words для .NET: загрузите и установите последнюю версию с сайта[здесь](https://releases.aspose.com/words/net/).
- IDE: Visual Studio или любая среда разработки C#.
- Базовые знания C#: понимание базового синтаксиса C# и концепций объектно-ориентированного программирования.
- Документ: образец документа Word (`Rendering.docx`) с полями формы ввода текста.

## Импортировать пространства имен

Прежде всего, вам необходимо импортировать необходимые пространства имен. Это своего рода строительные блоки, благодаря которым все работает без сбоев.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Хорошо, теперь, когда у нас есть готовые пространства имен, давайте приступим к делу!

## Шаг 1. Настройте проект

Прежде чем мы перейдем к коду, давайте убедимся, что наш проект настроен правильно.

## Создание проекта

1. Откройте Visual Studio. Начните с открытия Visual Studio или предпочитаемой вами среды разработки C#.
2.  Создайте новый проект: перейдите к`File > New > Project` . Выбирать`Console App (.NET Core)` или любой другой соответствующий тип проекта.
3.  Назовите свой проект: дайте вашему проекту осмысленное имя, например`AsposeWordsExportExample`.

## Добавление Aspose.Words

1.  Управление пакетами NuGet. Щелкните правой кнопкой мыши свой проект в обозревателе решений и выберите`Manage NuGet Packages`.
2.  Найдите Aspose.Words. В диспетчере пакетов NuGet найдите`Aspose.Words`.
3.  Установите Aspose.Words: нажмите`Install` чтобы добавить библиотеку Aspose.Words в ваш проект.

## Шаг 2. Загрузите документ Word

Теперь, когда наш проект настроен, давайте загрузим документ Word, содержащий поля формы ввода текста.

1. Укажите каталог документов. Определите путь к каталогу, в котором хранится ваш документ.
2.  Загрузите документ: используйте`Document` класс для загрузки документа Word.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3. Подготовьте каталог экспорта

Прежде чем экспортировать, давайте убедимся, что наш каталог экспорта готов. Здесь будут сохранены наш HTML-файл и изображения.

1. Определите каталог экспорта: укажите путь, по которому будут сохранены экспортированные файлы.
2. Проверьте и очистите каталог. Убедитесь, что каталог существует и пуст.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Шаг 4. Настройте параметры сохранения

Вот где происходит волшебство. Нам нужно настроить параметры сохранения, чтобы экспортировать поле формы ввода текста в виде обычного текста.

1.  Создать параметры сохранения: инициализировать новый`HtmlSaveOptions` объект.
2.  Установить параметр экспорта текста: настроить`ExportTextInputFormFieldAsText`собственность`true`.
3. Установить папку изображений: Определите папку, в которой будут сохраняться изображения.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Шаг 5. Сохраните документ в формате HTML.

Наконец, давайте сохраним документ Word как файл HTML, используя настроенные нами параметры сохранения.

1. Определите путь вывода: укажите путь, по которому будет сохранен HTML-файл.
2.  Сохраните документ: используйте`Save` метод`Document`класс для экспорта документа.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Заключение

И вот оно! Вы успешно экспортировали поле формы ввода текста в виде обычного текста с помощью Aspose.Words для .NET. Это руководство должно было дать вам четкий, пошаговый подход к решению этой задачи. Помните, что практика ведет к совершенству, поэтому продолжайте экспериментировать с различными опциями и настройками, чтобы увидеть, что еще вы можете сделать с Aspose.Words.

## Часто задаваемые вопросы

### Могу ли я экспортировать другие типы полей формы, используя тот же метод?

 Да, вы можете экспортировать другие типы полей формы, настроив различные свойства поля.`HtmlSaveOptions` сорт.

### Что делать, если в моем документе есть изображения?

 Изображения будут сохранены в указанной папке изображений. Обязательно установите`ImagesFolder` недвижимость в`HtmlSaveOptions`.

### Нужна ли мне лицензия для Aspose.Words?

 Да, вы можете получить бесплатную пробную версию[здесь](https://releases.aspose.com/) или купить лицензию[здесь](https://purchase.aspose.com/buy).

### Могу ли я настроить экспортированный HTML?

 Абсолютно! Aspose.Words предоставляет различные параметры для настройки вывода HTML. Обратитесь к[документация](https://reference.aspose.com/words/net/) для более подробной информации.

### Совместим ли Aspose.Words с .NET Core?

Да, Aspose.Words совместим с .NET Core, .NET Framework и другими платформами .NET.
