---
title: Встроить шрифты в документ PDF
linktitle: Встроить шрифты в документ PDF
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по встраиванию шрифтов в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

В этой статье представлено пошаговое руководство по использованию функции встраивания шрифтов в PDF-документ Aspose.Words для .NET. Мы рассмотрим фрагмент кода и подробно объясним каждую часть. К концу этого руководства вы сможете понять, как внедрить все шрифты в документ и создать PDF-файл со встроенными шрифтами с помощью Aspose.Words для .NET.

Прежде чем мы начнем, убедитесь, что в вашем проекте установлена и настроена библиотека Aspose.Words for .NET. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1. Определите путь к каталогу документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере предполагается, что документ называется «Rendering.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3. Настройте параметры сохранения PDF

 Чтобы встроить все шрифты в итоговый PDF-файл, нам нужно настроить`PdfSaveOptions` объект с`EmbedFullFonts` свойство установлено на`true`. Это гарантирует, что все шрифты, используемые в документе, будут включены в сгенерированный файл PDF.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## Шаг 4. Сохраните документ в формате PDF со встроенными шрифтами.

 Наконец, мы можем сохранить документ в виде файла PDF со встроенными шрифтами. Укажите имя выходного файла и`saveOptions` объект, который мы настроили на предыдущем шаге.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

Вот и все! Вы успешно внедрили все шрифты в документ и создали PDF-файл со встроенными шрифтами с помощью Aspose.Words для .NET.

### Пример исходного кода для Embedded All Fonts с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// В выходной PDF-файл будут встроены все шрифты, найденные в документе.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## Заключение

В этом руководстве мы узнали, как внедрить все шрифты в документ PDF с помощью Aspose.Words для .NET. Встраивание шрифтов гарантирует, что шрифты, указанные в документе, будут доступны и правильно отображены, даже если они не установлены в системе, в которой открыт PDF-файл. Это обеспечивает единый внешний вид и точное форматирование документов на разных устройствах и платформах. Не стесняйтесь исследовать дополнительные функции Aspose.Words для .NET, чтобы оптимизировать создание ваших PDF-документов со встроенными шрифтами.

### Часто задаваемые вопросы

#### В: Что такое встраивание шрифтов в документ PDF и почему это важно?
О: Встраивание шрифтов в документ PDF — это процесс включения всех шрифтов, используемых в документе, в сам файл PDF. Это гарантирует, что шрифты, указанные в документе, будут доступны и правильно отображены, даже если шрифты не установлены в системе, в которой открыт PDF-файл. Внедрение шрифтов важно для сохранения внешнего вида и форматирования документа, а также для обеспечения единообразного отображения шрифтов на разных устройствах и платформах.

#### Q: Как я могу внедрить все шрифты в документ PDF, используя Aspose.Words для .NET?
О: Чтобы внедрить все шрифты в документ PDF с помощью Aspose.Words for .NET, выполните следующие действия:

 Задайте путь к каталогу документов, заменив`"YOUR DOCUMENT DIRECTORY"` с фактическим путем каталога ваших документов.

 Загрузите документ, который хотите обработать, с помощью`Document` класс и путь к документу.

 Настройте параметры сохранения PDF, создав экземпляр`PdfSaveOptions` класс и установка`EmbedFullFonts` собственность на`true`. Это гарантирует, что все шрифты, используемые в документе, будут встроены в сгенерированный PDF-файл.

 Сохраните документ в формате PDF со встроенными шрифтами, используя`Save` метод`Document`объект, указав имя выходного файла и параметры сохранения, настроенные ранее.

#### В: Почему важно встраивать все шрифты в PDF-документ?
О: Внедрение всех шрифтов в PDF-документ важно для обеспечения правильного отображения документа, даже если указанные шрифты недоступны в системе, в которой открыт PDF-файл. Это помогает сохранить внешний вид, форматирование и удобочитаемость документа, гарантируя, что используемые шрифты одинаково отображаются на разных устройствах и платформах.

#### В: Каковы преимущества встраивания шрифтов в PDF-документ?
О: Преимущества встраивания шрифтов в PDF-документ:

Обеспечьте единый внешний вид документа: встроенные шрифты гарантируют, что документ будет отображаться точно так, как он был разработан, независимо от шрифтов, доступных в системе.

Сохранение форматирования: встроенные шрифты сохраняют форматирование и макет документа, избегая замены шрифтов и изменения внешнего вида.

Улучшенная читабельность: встраивание шрифтов обеспечивает лучшую читаемость документа, поскольку указанные шрифты используются для отображения текста, даже если исходные шрифты недоступны.

#### В: Увеличивает ли встраивание всех шрифтов размер файла PDF?
О: Да, встраивание всех шрифтов в PDF-документ может увеличить размер создаваемого PDF-файла, так как данные шрифта должны быть включены в файл. Однако для большинства документов это увеличение размера обычно незначительно, и преимущества встроенных шрифтов часто перевешивают это незначительное увеличение размера.

#### В: Могу ли я выбрать определенные шрифты для встраивания в PDF-документ?
 О: Да, с помощью Aspose.Words для .NET вы можете выбрать определенные шрифты для встраивания в документ PDF, используя расширенные параметры конфигурации. Например, вы можете использовать`SubsetFonts` собственность`PdfSaveOptions` объект, чтобы указать, какие шрифты следует включить, или используйте дополнительные параметры для установки пользовательских фильтров выбора шрифтов.