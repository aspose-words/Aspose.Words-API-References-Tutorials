---
title: Очистить повторяющийся стиль
linktitle: Очистить повторяющийся стиль
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по удалению повторяющихся стилей в документе с помощью Aspose.Words для .NET. Полный исходный код включен.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

В этом руководстве мы пошагово рассмотрим исходный код C#, чтобы очистить повторяющиеся стили с помощью Aspose.Words для .NET. Эта функция помогает удалить повторяющиеся стили из документа.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, который хотим очистить. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Считайте стили перед очисткой

Прежде чем приступить к очистке, посчитаем количество стилей, присутствующих в документе. Используйте следующий код для отображения количества стилей:

```csharp
Console.WriteLine(doc.Styles.Count);
```

Этот оператор отображает количество стилей, присутствующих в документе.

## Шаг 4. Удалите повторяющиеся стили.

Теперь давайте очистим документ от повторяющихся стилей. Используйте следующий код для выполнения очистки:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 Этот код удаляет повторяющиеся стили из документа, используя указанные параметры. В этом примере мы включили`DuplicateStyle` возможность очистки повторяющихся стилей.

## Шаг 5: Подсчитайте стили после очистки

Сделав очистку, мы снова посчитаем количество стилей, чтобы проверить, не уменьшилось ли оно. Используйте следующий код, чтобы отобразить количество новых стилей:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

Этот оператор отображает количество стилей, оставшихся после очистки.

### Пример исходного кода для очистки повторяющегося стиля с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Количество стилей перед очисткой.
	Console.WriteLine(doc.Styles.Count);

	// Удаляет повторяющиеся стили из документа.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//Уменьшено количество стилей после очистки.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```