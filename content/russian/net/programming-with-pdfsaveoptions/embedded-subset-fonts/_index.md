---
title: Внедрение подмножества шрифтов в документ PDF
linktitle: Внедрение подмножества шрифтов в документ PDF
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по внедрению подмножеств шрифтов в документ PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---

В этой статье представлено пошаговое руководство по использованию функции встраивания подмножества шрифтов в Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как встраивать подмножества шрифтов в документ и создавать PDF-файл, содержащий только глифы, используемые в документе.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере предполагается, что документ называется «Rendering.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 3. Настройте параметры сохранения в формате PDF.

 Чтобы создать PDF-файл, содержащий только подмножества шрифтов, используемых в документе, нам нужно настроить`PdfSaveOptions` объект с`EmbedFullFonts` свойство установлено на`false`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

## Шаг 4. Сохраните документ в формате PDF с подмножествами шрифтов.

 Наконец, мы можем сохранить документ в формате PDF, используя подмножества шрифтов. Укажите имя выходного файла и`saveOptions` объект, который мы настроили на предыдущем шаге.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);
```

Вот и все ! Вы успешно внедрили подмножества шрифтов в документ и создали PDF-файл, содержащий только глифы, используемые в документе, с помощью Aspose.Words для .NET.

### Пример исходного кода для внедрения подмножеств шрифтов с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Выходной PDF-файл будет содержать подмножества шрифтов в документе.
	// В шрифты PDF включаются только глифы, используемые в документе.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddSubsetFonts.pdf", saveOptions);

```

## Заключение

В этом руководстве мы узнали, как встраивать подмножества шрифтов в документ PDF с помощью Aspose.Words для .NET. Внедрение подмножеств шрифтов помогает уменьшить размер файла PDF, сохраняя при этом внешний вид документа за счет использования только фактически используемых символов. Это обеспечивает лучшую совместимость и производительность при просмотре и печати PDF. Вы можете продолжить изучение функций Aspose.Words для .NET, чтобы оптимизировать создание ваших PDF-документов со встроенными подмножествами шрифтов.

### Часто задаваемые вопросы

#### Вопрос. Что такое встраивание подмножеств шрифтов в PDF-документ?
О: Встраивание подмножеств шрифтов в документ PDF — это процесс включения только глифов, используемых в документе, а не всех полных шрифтов. Это уменьшает размер файла PDF за счет включения только данных шрифта, необходимых для отображения символов, фактически используемых в документе.

#### В: В чем разница между внедрением полных шрифтов и внедрением подмножеств шрифтов?
О: Полное встраивание шрифтов означает включение всех шрифтов, используемых в документе, в файл PDF, что гарантирует, что документ будет отображаться точно так, как он был разработан, но может увеличить размер файла PDF. Напротив, встраивание подмножеств шрифтов содержит только глифы, используемые в документе, тем самым уменьшая размер файла PDF, но ограничивая возможность точно воспроизвести внешний вид документа, если дополнительные символы будут добавлены позже.

#### В: Как я могу встроить подмножества шрифтов в документ PDF с помощью Aspose.Words для .NET?
О: Чтобы встроить подмножества шрифтов в документ PDF с помощью Aspose.Words for .NET, выполните следующие действия:

 Задайте путь к каталогу документов, заменив`"YOUR DOCUMENT DIRECTORY"` с фактическим путем каталога ваших документов.

 Загрузите документ, который хотите обработать, с помощью`Document` класс и путь к документу.

 Настройте параметры сохранения PDF, создав экземпляр`PdfSaveOptions` класс и установка`EmbedFullFonts` собственность на`false`Это гарантирует, что в файл PDF будут включены только подмножества шрифтов, используемые в документе.

 Сохраните документ в формате PDF с внедренными подмножествами шрифтов с помощью`Save` метод`Document` объект, указав имя выходного файла и параметры сохранения, настроенные ранее.

#### В: Каковы преимущества внедрения подмножеств шрифтов в PDF-документ?
О: Преимущества внедрения подмножеств шрифтов в PDF-документ:

Уменьшенный размер файла PDF: за счет включения только глифов, используемых в документе, размер файла PDF уменьшается по сравнению с внедрением полных шрифтов.

Сохранение внешнего вида документа: подмножества шрифтов, включенные в файл PDF, позволяют воспроизвести внешний вид документа, используя только фактически используемые символы.

Совместимость с ограничениями лицензии: встраивание подмножеств шрифтов может быть предпочтительнее в тех случаях, когда полные шрифты не могут быть внедрены на законных основаниях из-за лицензионных ограничений.