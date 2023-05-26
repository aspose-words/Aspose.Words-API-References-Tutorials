---
title: Преобразование метафайлов в EMF или WMF
linktitle: Преобразование метафайлов в EMF или WMF
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по преобразованию метафайлов в форматы EMF или WMF при преобразовании документа в HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

В этом руководстве мы познакомим вас с исходным кодом C# для преобразования метафайлов в формат EMF или WMF с помощью Aspose.Words для .NET. Эта функция позволяет преобразовывать изображения в формате метафайла в более совместимые форматы, такие как EMF или WMF, при преобразовании документа в HTML.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2. Вставка изображения в документ

На этом шаге мы вставим изображение в документ, который нужно преобразовать. Используйте следующий код, чтобы вставить изображение из источника данных с помощью тега HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Этот код создает экземпляр`Document` и`DocumentBuilder` для построения документа. Он вставляет`<img>` тег в документ с изображением в кодировке base64.

## Шаг 3. Установите параметры сохранения HTML

Теперь мы установим параметры сохранения HTML, включая формат метафайла, который будет использоваться для изображений. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Этот код создает экземпляр`HtmlSaveOptions` и наборы`MetafileFormat` к`HtmlMetafileFormat.EmfOrWmf` чтобы указать, что метафайлы должны быть преобразованы в формат EMF или WMF при преобразовании в HTML.

## Шаг 4: Преобразование и сохранение документа в формате HTML

Наконец, мы преобразуем документ в HTML, используя ранее определенные параметры сохранения HTML. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Этот код преобразует документ в HTML и сохраняет его в файл с преобразованными метафайлами в формате EMF или WMF в зависимости от установленных параметров сохранения.

### Пример исходного кода для преобразования метафайлов в EMF или Wmf с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.

Теперь вы узнали, как преобразовывать метафайлы в форматы EMF или WMF при преобразовании документа в HTML с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете легко управлять метафайлами в преобразованных HTML-документах.