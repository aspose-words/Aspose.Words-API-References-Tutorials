---
title: Установить параметры страницы и форматирование раздела
linktitle: Установить параметры страницы и форматирование раздела
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по настройке макета документа и форматирования разделов с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы настроить макет и форматирование разделов с помощью Aspose.Words для .NET. Эта функция позволяет установить ориентацию страницы, поля и размер бумаги.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Создание документа

На этом шаге мы создадим новый документ. Используйте следующий код для создания документа и инициализации конструктора:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

## Шаг 3: Настройка макета и сохранение документа

Теперь давайте настроим макет документа. Используйте следующий код, чтобы установить ориентацию, поля и размер бумаги:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Этот код установит альбомную ориентацию страницы, левое поле 50 и размер бумаги 10x14.

### Пример исходного кода для настройки параметров страницы и форматирования разделов с использованием Aspose.Words для .NET

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

Теперь вы узнали, как настроить макет и форматирование разделов документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете легко настроить макет и форматирование ваших собственных документов.