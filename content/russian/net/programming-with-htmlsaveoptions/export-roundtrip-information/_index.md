---
title: Экспорт информации о туда и обратно
linktitle: Экспорт информации о туда и обратно
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по экспорту обратной информации при сохранении документа в формате HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

В этом руководстве мы познакомим вас с исходным кодом C# для экспорта информации туда и обратно из документа с помощью Aspose.Words для .NET. Эта функция позволяет включать информацию о возврате в экспортируемый HTML-файл, что упрощает извлечение изменений, внесенных в исходный документ.

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

Теперь мы настроим параметры сохранения HTML для экспорта информации о документе. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Этот код создает экземпляр`HtmlSaveOptions`и устанавливает`ExportRoundtripInformation` возможность`true` для включения информации о поездке туда и обратно при экспорте.

## Шаг 4. Преобразование и сохранение документа в HTML.

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, настроенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Этот код преобразует документ в HTML, включая обратную информацию, и сохраняет экспортированный HTML-файл в указанный каталог.

### Пример исходного кода для экспорта информации о двустороннем пути с использованием Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.