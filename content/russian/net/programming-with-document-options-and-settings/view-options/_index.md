---
title: Посмотреть варианты
linktitle: Посмотреть варианты
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по настройке параметров отображения документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/view-options/
---

В этом руководстве мы познакомим вас с исходным кодом C# для настройки параметров отображения с помощью Aspose.Words для .NET. Эта функция позволяет настроить режим просмотра и уровень масштабирования документа.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, для которого хотим настроить параметры отображения. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Настройка параметров отображения

Теперь настроим параметры отображения документа. Используйте следующий код, чтобы установить режим отображения и уровень масштабирования:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Этот код устанавливает режим просмотра «PageLayout» и уровень масштабирования 50%.

### Пример исходного кода для параметров просмотра с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Обязательно укажите правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как настроить параметры отображения документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете легко настроить отображение своих собственных документов.