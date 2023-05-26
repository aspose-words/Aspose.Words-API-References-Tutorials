---
title: Перечислить свойства
linktitle: Перечислить свойства
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по перечислению свойств документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/enumerate-properties/
---

В этом руководстве мы познакомим вас с исходным кодом C# для перечисления свойств документа с помощью Aspose.Words для .NET. Эта функция позволяет вам получить доступ к встроенным и пользовательским свойствам документа.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, свойства которого мы хотим перечислить. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3: перечисление свойств

Теперь давайте перечислим свойства документа, как встроенные, так и пользовательские. Используйте следующий код:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Этот код отображает имя документа, а затем перечисляет встроенные и настраиваемые свойства с указанием их имени и значения.

### Пример исходного кода для перечисления свойств с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как перечислять свойства документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, приведенному в этом руководстве, вы сможете легко получить доступ к свойствам ваших собственных документов и просмотреть их.

