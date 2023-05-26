---
title: Конвертировать метафайлы в SVG
linktitle: Конвертировать метафайлы в SVG
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по преобразованию метафайлов в формат SVG при преобразовании документа в HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

В этом руководстве мы познакомим вас с исходным кодом C# для преобразования метафайлов в формат SVG с помощью Aspose.Words для .NET. Эта функция позволяет преобразовывать метафайлы в формат SVG при преобразовании документа в HTML.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2. Вставка изображения SVG в документ

На этом этапе мы вставим изображение SVG в документ, который нужно преобразовать. Используйте следующий код, чтобы вставить изображение SVG с помощью тега HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Этот код создает экземпляр`Document` и`DocumentBuilder` для построения документа. Он вставляет`<svg>` тег, содержащий`<polygon>` элемент с атрибутами для определения формы и стиля изображения SVG.

## Шаг 3. Установите параметры сохранения HTML

Теперь мы установим параметры сохранения HTML, указав, что метафайлы должны быть преобразованы в формат SVG. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Этот код создает экземпляр`HtmlSaveOptions` и наборы`MetafileFormat` к`HtmlMetafileFormat.Svg` чтобы указать, что метафайлы должны быть преобразованы в формат SVG при преобразовании в HTML.

## Шаг 4: Преобразование и сохранение документа в формате HTML

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, определенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Этот код преобразует документ в HTML и сохраняет его в файл с метафайлами, преобразованными в SVG.

### Пример исходного кода для преобразования метафайлов в Svg с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
