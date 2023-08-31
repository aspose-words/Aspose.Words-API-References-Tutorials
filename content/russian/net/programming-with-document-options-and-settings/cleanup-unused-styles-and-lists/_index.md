---
title: Очистка неиспользуемых стилей и списков
linktitle: Очистка неиспользуемых стилей и списков
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по очистке неиспользуемых стилей и списков в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы очистить неиспользуемые стили и списки с помощью Aspose.Words для .NET. Эта функция позволяет удалять стили и списки, которые не используются в документе.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, содержащий неиспользуемые стили и списки, которые мы хотим очистить. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Подсчитайте стили и списки перед очисткой

Перед очисткой посчитаем количество стилей и списков, присутствующих в документе. Используйте следующий код для отображения счетчиков:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

Эти инструкции показывают количество стилей и списков, присутствующих в документе до очистки.

## Шаг 4. Очистите неиспользуемые стили и списки.

Теперь давайте удалим из документа неиспользуемые стили и списки. Используйте следующий код для выполнения очистки:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 Этот код очищает неиспользуемые стили и списки из документа, используя указанные параметры. В этом примере мы включили`UnusedStyles` возможность удалить неиспользуемые стили и отключить`UnusedLists` возможность сохранять списки, даже если они не используются.

## Шаг 5. Подсчитайте стили и списки после очистки

После очистки мы еще раз посчитаем стили и списки, чтобы проверить, не свернулись ли они. Используйте следующий код для отображения новых счетчиков:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

В этих инструкциях показано количество стилей и списков, оставшихся после очистки.

### Пример исходного кода для очистки неиспользуемых стилей и списков с помощью Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// В сочетании со встроенными стилями документ теперь имеет восемь стилей.
	// Пользовательский стиль помечается как «использованный», если в документе есть какой-либо текст.
	// отформатирован в этом стиле. Это означает, что 4 добавленных нами стиля в настоящее время не используются.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//Очищает неиспользуемые стили и списки из документа в зависимости от заданных CleanupOptions.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 Обязательно укажите правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как очистить неиспользуемые стили и списки из документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете легко применить эту функцию к своим собственным документам.

