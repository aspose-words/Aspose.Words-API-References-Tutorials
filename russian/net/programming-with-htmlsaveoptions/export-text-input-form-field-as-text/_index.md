---
title: Экспорт поля формы ввода текста в виде текста
linktitle: Экспорт поля формы ввода текста в виде текста
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по экспорту полей формы ввода текста в виде обычного текста с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---

В этом руководстве мы познакомим вас с исходным кодом C# для экспорта полей формы ввода текста в виде обычного текста с помощью Aspose.Words для .NET. Эта функция позволяет экспортировать поля формы ввода текста как читаемый текст, а не как элементы ввода HTML.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ для экспорта. Используйте следующий код для загрузки документа из указанного каталога:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Этот код создает экземпляр`Document` загрузив документ из указанного каталога.

## Шаг 3. Настройка параметров резервного копирования HTML

Теперь мы настроим параметры сохранения HTML для экспорта полей формы ввода текста в виде обычного текста. Используйте следующий код:

```csharp
string imagesDir = Path. Combine(ArtifactsDir, "Images");

// Указанная папка должна существовать и быть пустой.
if (Directory.Exists(imagesDir))
Directory. Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);

HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
ExportTextInputFormFieldAsText = true,
ImagesFolder = imagesDir
};
```

 Этот код создает экземпляр`HtmlSaveOptions`и устанавливает`ExportTextInputFormFieldAsText` возможность`true`экспортировать поля формы ввода текста как обычный текст. Кроме того, он указывает папку, в которой будут сохранены извлеченные изображения.

## Шаг 4: Преобразование и сохранение документа в формате HTML

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, настроенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);
```

Этот код преобразует документ в HTML, экспортируя поля формы ввода текста как обычный текст, и сохраняет экспортированный HTML-файл в указанный каталог.

### Пример исходного кода для экспорта поля формы ввода текста в виде текста с использованием Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	string imagesDir = Path.Combine(ArtifactsDir, "Images");

	// Указанная папка должна существовать и должна быть пустой.
	if (Directory.Exists(imagesDir))
		Directory.Delete(imagesDir, true);

	Directory.CreateDirectory(imagesDir);

	// Установите параметр, чтобы экспортировать поля формы как обычный текст, а не как элементы ввода HTML.
	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		ExportTextInputFormFieldAsText = true, ImagesFolder = imagesDir
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportTextInputFormFieldAsText.html", saveOptions);

```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.