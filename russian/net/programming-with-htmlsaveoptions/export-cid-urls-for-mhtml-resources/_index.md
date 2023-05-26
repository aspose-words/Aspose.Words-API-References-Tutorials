---
title: Экспорт URL-адресов Cid для ресурсов Mhtml
linktitle: Экспорт URL-адресов Cid для ресурсов Mhtml
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по экспорту URL-адресов CID ресурсов MHTML при сохранении документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

В этом руководстве мы рассмотрим исходный код C# для экспорта URL-адресов CID для ресурсов MHTML с помощью Aspose.Words для .NET. Эта функция позволяет экспортировать URL-адреса CID ресурсов MHTML при сохранении документа в формате MHTML.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ для экспорта. Используйте следующий код для загрузки документа из указанного каталога:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Этот код создает экземпляр`Document` загрузив документ из указанного каталога.

## Шаг 3. Настройка параметров резервного копирования HTML

Теперь мы настроим параметры сохранения HTML для экспорта URL-адресов CID ресурсов MHTML. Используйте следующий код:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Этот код создает экземпляр`HtmlSaveOptions` с установленным форматом сохранения MHTML. Он также позволяет экспортировать URL-адреса CID ресурсов MHTML, установив`ExportCidUrlsForMhtmlResources` к`true`.

## Шаг 4. Преобразование и сохранение документа в MHTML

Наконец, мы преобразуем документ в MHTML, используя параметры сохранения HTML, настроенные ранее. Используйте следующий код:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Этот код преобразует документ в MHTML и сохраняет его в файл с URL-адресами CID экспортированных ресурсов MHTML.

### Пример исходного кода для экспорта URL-адресов Cid для ресурсов Mhtml с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Обязательно укажите правильный путь к каталогу документов в`dataDir` переменная.

Теперь вы узнали, как экспортировать URL-адреса CID ресурсов MHTML при сохранении документа в формате MHTML с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете легко управлять URL-адресами CID в экспортированных документах MHTML.

