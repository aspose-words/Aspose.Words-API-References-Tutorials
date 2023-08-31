---
title: Добавить пользовательские свойства документа
linktitle: Добавить пользовательские свойства документа
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по добавлению настраиваемых свойств в документ с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/add-custom-document-properties/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы добавить настраиваемые свойства в документ с помощью Aspose.Words для .NET. Эта функция позволяет добавлять в документ пользовательскую информацию.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, к которому мы хотим добавить настраиваемые свойства. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Добавьте пользовательские свойства

Теперь давайте добавим в документ пользовательские свойства. Используйте следующий код, чтобы добавить свойства:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Этот код сначала проверяет, существует ли свойство «Авторизованный» в пользовательских свойствах. Если он существует, процесс прерывается. В противном случае в документ добавляются настраиваемые свойства.

### Пример исходного кода для добавления пользовательских свойств документа с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как добавлять пользовательские свойства в документ с помощью Aspose.Words для .NET. Следуя пошаговому руководству, приведенному в этом руководстве, вы сможете легко добавлять собственные настраиваемые свойства в свои документы.