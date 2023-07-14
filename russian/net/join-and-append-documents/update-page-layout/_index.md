---
title: Обновить макет страницы
linktitle: Обновить макет страницы
second_title: API обработки документов Aspose.Words
description: Узнайте, как обновить макет страницы при объединении и добавлении документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/update-page-layout/
---

Это руководство проведет вас через процесс использования функции «Обновить макет страницы» Aspose.Words для .NET. Эта функция обеспечивает правильное обновление макета страницы при объединении и добавлении документов Word.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете загрузить его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1: Инициализируйте каталоги документов

 Во-первых, вам нужно указать путь к папке с документами. Измените значение параметра`dataDir`переменная на путь, где находятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный и целевой документы

 Далее вам нужно загрузить исходный и конечный документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3: Обновите макет страницы для целевого документа

 Чтобы обеспечить правильное обновление макета страницы перед добавлением исходного документа, вы можете вызвать метод`UpdatePageLayout` метод в целевом документе.

```csharp
dstDoc.UpdatePageLayout();
```

## Шаг 4: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр обеспечивает сохранение исходного форматирования во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5: снова обновите макет страницы

 После добавления исходного документа необходимо вызвать`UpdatePageLayout` метод в целевом документе еще раз, чтобы гарантировать, что любые изменения, сделанные после операции добавления, будут отражены в визуализированных выходных данных.

```csharp
dstDoc.UpdatePageLayout();
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией «Обновить макет страницы».`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### Пример исходного кода для обновления макета страницы с использованием Aspose.Words для .NET

Вот полный исходный код функции «Обновить макет страницы» на C# с использованием Aspose.Words для .NET:

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//Если конечный документ преобразуется в PDF, изображение и т. д.
	// или UpdatePageLayout вызывается перед исходным документом. Прилагается,
	// тогда любые изменения, сделанные после, не будут отражены в отображаемом выводе.
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// Чтобы изменения были обновлены в отображаемом выводе, необходимо снова вызвать UpdatePageLayout.
	// Если не вызываться снова, добавленный документ не появится в выводе следующего рендеринга.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

Вот и все! Вы успешно внедрили функцию обновления макета страницы с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенный контент с правильно обновленным макетом страницы.