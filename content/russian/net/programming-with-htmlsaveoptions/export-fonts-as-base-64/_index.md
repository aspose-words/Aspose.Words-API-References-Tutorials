---
title: Экспортировать шрифты в формате Base 64
linktitle: Экспортировать шрифты в формате Base 64
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по экспорту шрифтов Base 64 при сохранении документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

В этом руководстве мы познакомим вас с исходным кодом C# для экспорта шрифтов Base 64 с помощью Aspose.Words для .NET. Эта функция позволяет экспортировать шрифты как данные Base 64 при сохранении документа в формате HTML.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ для экспорта. Используйте следующий код для загрузки документа из указанного каталога:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Этот код создает экземпляр`Document` Загрузив документ из указанного каталога.

## Шаг 3. Настройка параметров резервного копирования HTML

Теперь мы настроим параметры сохранения HTML для экспорта шрифтов Base 64. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Этот код создает экземпляр`HtmlSaveOptions` и наборы`ExportFontsAsBase64` к`true` чтобы указать, что шрифты должны экспортироваться как данные Base 64 при сохранении в формате HTML.

## Шаг 4. Преобразование и сохранение документа в HTML.

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, настроенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Этот код преобразует документ в HTML и сохраняет его в файл со шрифтами, экспортированными как данные Base 64.

### Пример исходного кода для экспорта шрифтов в формате Base 64 с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.

Теперь вы узнали, как экспортировать шрифты Base 64 при сохранении документа в формате HTML с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете легко экспортировать шрифты и встроить их в свои HTML-документы.