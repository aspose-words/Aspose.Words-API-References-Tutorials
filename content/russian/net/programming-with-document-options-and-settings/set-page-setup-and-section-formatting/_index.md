---
title: Установите настройки страницы и форматирование разделов
linktitle: Установите настройки страницы и форматирование разделов
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по настройке макета документа и форматированию разделов с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

В этом руководстве мы познакомим вас с исходным кодом C# для настройки макета и форматирования разделов с помощью Aspose.Words для .NET. Эта функция позволяет вам установить ориентацию страницы, поля и размер бумаги.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Создание документа

На этом этапе мы создадим новый документ. Используйте следующий код для создания документа и инициализации конструктора:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

## Шаг 3. Настройка макета и сохранение документа.

Теперь настроим макет документа. Используйте следующий код, чтобы установить ориентацию, поля и размер бумаги:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Этот код установит альбомную ориентацию страницы, левое поле — 50, а размер бумаги — 10x14.

### Пример исходного кода для установки параметров страницы и форматирования разделов с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 Обязательно укажите правильный путь к каталогу, в котором вы хотите сохранить документ в`dataDir` переменная.

Теперь вы узнали, как настроить макет и форматирование разделов документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете легко настроить макет и форматирование своих собственных документов.