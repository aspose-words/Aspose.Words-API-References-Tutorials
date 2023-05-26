---
title: Экспорт структуры документа
linktitle: Экспорт структуры документа
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по экспорту структуры документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/export-document-structure/
---

В этой статье представлено пошаговое руководство по использованию функции «Экспорт структуры документа» в Aspose.Words для .NET. Мы подробно объясним каждую часть кода. В конце этого руководства вы сможете понять, как экспортировать структуру документа и создать PDF-файл с видимой структурой документа.

Прежде чем начать, убедитесь, что вы установили и настроили библиотеку Aspose.Words for .NET в своем проекте. Вы можете найти библиотеку и инструкции по установке на веб-сайте Aspose.

## Шаг 1: Определите каталог документов

 Для начала вам нужно указать путь к каталогу, в котором находятся ваши документы. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2: Загрузите документ

Далее нам нужно загрузить документ, который мы хотим обработать. В этом примере предполагается, что документ называется «Paragraphs.docx» и находится в указанном каталоге документов.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Шаг 3. Настройте параметры сохранения в формате PDF.

 Чтобы экспортировать структуру документа и сделать ее видимой на панели навигации «Содержимое» Adobe Acrobat Pro при редактировании файла PDF, нам необходимо настроить`PdfSaveOptions` объект с`ExportDocumentStructure` свойство установлено на`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Шаг 4. Сохраните документ в формате PDF со структурой документа.

Наконец, мы можем сохранить документ в формате PDF, используя параметры сохранения, настроенные ранее.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Вот и все ! Вы успешно экспортировали структуру документа и создали PDF-файл со структурой документа, видимой с помощью Aspose.Words для .NET.

### Пример исходного кода для экспорта структуры документа с помощью Aspose.Words для .NET


```csharp

            // Путь к каталогу документов.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Размер файла будет увеличен, а структура будет видна на панели навигации «Содержание».
            // Adobe Acrobat Pro при редактировании файла .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```
