---
title: Разрешить имена шрифтов
linktitle: Разрешить имена шрифтов
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по устранению отсутствующих имен шрифтов при преобразовании в HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/resolve-font-names/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы разрешить отсутствующие имена шрифтов с помощью Aspose.Words для .NET. Эта функция позволяет автоматически разрешать отсутствующие имена шрифтов при преобразовании документа в HTML.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ для обработки. Используйте следующий код для загрузки документа из указанного каталога:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Этот код создает экземпляр`Document` загрузив документ из указанного каталога.

## Шаг 3. Настройка параметров резервного копирования HTML

Теперь мы настроим параметры сохранения HTML, чтобы разрешить отсутствующие имена шрифтов во время преобразования. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Этот код создает экземпляр`HtmlSaveOptions`и устанавливает`ResolveFontNames` возможность`true` для разрешения отсутствующих имен шрифтов при преобразовании в HTML. Так же`PrettyFormat` опция установлена на`true` чтобы получить красиво отформатированный HTML-код.

## Шаг 4: Преобразование и сохранение документа в формате HTML

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, настроенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Этот код преобразует документ в HTML, автоматически разрешая отсутствующие имена шрифтов, и сохраняет преобразованный файл HTML в указанный каталог.

### Пример исходного кода для разрешения имен шрифтов с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.