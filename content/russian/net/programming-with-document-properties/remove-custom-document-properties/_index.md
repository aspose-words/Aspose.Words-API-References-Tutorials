---
title: Удалить пользовательские свойства документа
linktitle: Удалить пользовательские свойства документа
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по удалению пользовательских свойств из документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/remove-custom-document-properties/
---

В этом руководстве мы познакомим вас с исходным кодом C#, чтобы удалить пользовательские свойства из документа с помощью Aspose.Words для .NET. Эта функция позволяет удалить определенное пользовательское свойство из документа.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, из которого мы хотим удалить пользовательские свойства. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Удаление пользовательских свойств

Теперь давайте удалим конкретное пользовательское свойство из документа. Используйте следующий код:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Этот код удаляет пользовательское свойство «Дата авторизации» из документа. Вы можете заменить «Дата авторизации» на имя пользовательского свойства, которое вы хотите удалить.

### Пример исходного кода для удаления пользовательских свойств документа с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как удалить пользовательские свойства из документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, приведенному в этом руководстве, вы сможете легко удалить настраиваемые свойства из своих документов.