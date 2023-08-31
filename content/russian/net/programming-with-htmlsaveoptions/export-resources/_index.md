---
title: Экспорт ресурсов
linktitle: Экспорт ресурсов
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по экспорту ресурсов документа при сохранении в формате HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/export-resources/
---

В этом руководстве мы познакомим вас с исходным кодом C# для экспорта ресурсов документа с помощью Aspose.Words для .NET. Эта функция позволяет экспортировать ресурсы, например шрифты, во внешние файлы при сохранении документа в формате HTML.

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

Теперь мы настроим параметры сохранения HTML для экспорта ресурсов документа. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://пример.com/ресурсы"
};
```

 Этот код создает экземпляр`HtmlSaveOptions` и устанавливает следующие параметры:

- `CssStyleSheetType` установлен на`CssStyleSheetType.External`для экспорта таблицы стилей CSS во внешний файл.
- `ExportFontResources` установлен на`true` для экспорта ресурсов шрифта.
- `ResourceFolder` указывает каталог назначения, в котором будут сохранены ресурсы.
- `ResourceFolderAlias` указывает псевдоним URL, который будет использоваться для доступа к ресурсам.

## Шаг 4: Преобразование и сохранение документа в формате HTML

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, настроенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Этот код преобразует документ в HTML и сохраняет ресурсы в указанном каталоге, используя указанный псевдоним URL.

### Пример исходного кода для экспорта ресурсов с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://пример.com/ресурсы"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.