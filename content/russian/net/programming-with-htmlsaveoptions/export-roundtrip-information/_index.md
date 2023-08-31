---
title: Экспорт информации о пути туда и обратно
linktitle: Экспорт информации о пути туда и обратно
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по экспорту информации о пути туда и обратно при сохранении документа в формате HTML с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы экспортировать информацию о пути туда и обратно из документа с помощью Aspose.Words для .NET. Эта функция позволяет включать в экспортируемый HTML-файл информацию о цикле приема-передачи, что упрощает извлечение изменений, внесенных в исходный документ.

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

Теперь мы настроим параметры сохранения HTML, чтобы экспортировать информацию о двустороннем обходе документа. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Этот код создает экземпляр`HtmlSaveOptions`и устанавливает`ExportRoundtripInformation` возможность`true` включить информацию о пути туда и обратно при экспорте.

## Шаг 4: Преобразование и сохранение документа в формате HTML

Наконец, мы преобразуем документ в HTML, используя параметры сохранения HTML, настроенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Этот код преобразует документ в HTML, включая информацию о циклическом обходе, и сохраняет экспортированный HTML-файл в указанный каталог.

### Пример исходного кода для экспорта информации о круговых поездках с использованием Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.