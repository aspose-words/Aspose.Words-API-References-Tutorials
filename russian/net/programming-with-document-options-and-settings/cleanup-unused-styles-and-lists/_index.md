---
title: Очистка неиспользуемых стилей и списков
linktitle: Очистка неиспользуемых стилей и списков
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по очистке неиспользуемых стилей и списков в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы очистить неиспользуемые стили и списки с помощью Aspose.Words для .NET. Эта функция позволяет удалять стили и списки, которые не используются в документе.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, содержащий неиспользуемые стили и списки, которые мы хотим очистить. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Подсчитайте стили и списки перед очисткой

Перед очисткой посчитаем количество стилей и списков, присутствующих в документе. Используйте следующий код для отображения счетчиков:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Эти инструкции показывают количество стилей и списков, присутствующих в документе перед очисткой.

## Шаг 4. Очистите неиспользуемые стили и списки

Теперь давайте удалим из документа неиспользуемые стили и списки. Используйте следующий код для выполнения очистки:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Этот код очищает документ от неиспользуемых стилей и списков с помощью указанных параметров. В этом примере мы включили`UnusedStyles` возможность удалить неиспользуемые стили и отключить`UnusedLists` возможность сохранить списки, даже если они не используются.

## Шаг 5: Подсчет стилей и списков после очистки

После очистки мы снова посчитаем стили и списки, чтобы проверить, не свернулись ли они. Используйте следующий код для отображения новых счетчиков:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

В этих инструкциях указано количество стилей и списков, оставшихся после очистки.

### Пример исходного кода для очистки неиспользуемых стилей и списков с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// В сочетании со встроенными стилями документ теперь имеет восемь стилей.
	// Пользовательский стиль помечается как «используемый», пока в документе есть текст.
	// оформлен в этом стиле. Это означает, что 4 добавленных нами стиля в настоящее время не используются.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Удаляет из документа неиспользуемые стили и списки в зависимости от заданных параметров очистки.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как очистить документ от неиспользуемых стилей и списков с помощью Aspose.Words for .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете легко применить эту функцию к своим собственным документам.

