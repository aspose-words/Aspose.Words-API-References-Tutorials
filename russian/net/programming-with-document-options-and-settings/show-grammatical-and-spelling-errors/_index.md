---
title: Показать грамматические и орфографические ошибки
linktitle: Показать грамматические и орфографические ошибки
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по отображению грамматических и орфографических ошибок в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-options-and-settings/show-grammatical-and-spelling-errors/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы включить отображение грамматических и орфографических ошибок с помощью Aspose.Words для .NET. Эта функция позволяет просматривать грамматические и орфографические ошибки в документе.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, для которого мы хотим отобразить грамматические и орфографические ошибки. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Включите отображение ошибок

Теперь включим отображение грамматических и орфографических ошибок в документе. Используйте следующий код, чтобы включить отображение ошибок:

```csharp
doc. ShowGrammaticalErrors = true;
doc. ShowSpellingErrors = true;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");
```

Этот код включает отображение грамматических ошибок (`ShowGrammaticalErrors`) и орфографические ошибки (`ShowSpellingErrors`) в документе.

### Пример исходного кода для отображения грамматических и орфографических ошибок с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.ShowGrammaticalErrors = true;
	doc.ShowSpellingErrors = true;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ShowGrammaticalAndSpellingErrors.docx");

```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как включить отображение грамматических и орфографических ошибок в документе с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете легко включить эту функцию в свои собственные документы.