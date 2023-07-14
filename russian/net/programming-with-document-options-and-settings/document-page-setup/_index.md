---
title: Настройка страницы документа
linktitle: Настройка страницы документа
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по настройке макета документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/document-page-setup/
---

В этом руководстве мы познакомим вас с исходным кодом C# для настройки макета документа с помощью Aspose.Words для .NET. Эта функция позволяет вам установить режим макета, количество символов в строке и количество строк на странице.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, который хотим настроить. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3: Настройка макета

Теперь давайте настроим макет документа. Используйте следующий код, чтобы установить режим макета, количество символов в строке и количество строк на странице:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Этот код устанавливает режим макета «Сетка», а затем указывает количество символов в строке и количество строк на странице.

### Пример исходного кода для настройки страницы документа с использованием Aspose.Words для .NET


```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Установите режим макета для раздела, позволяющий определить поведение сетки документа.
	// Обратите внимание, что вкладка «Сетка документа» становится видимой в диалоговом окне «Параметры страницы» MS Word.
	// если какой-либо азиатский язык определен как язык редактирования.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как настроить макет документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, приведенному в этом руководстве, вы сможете легко настроить макет своих собственных документов.