---
title: Перечислить свойства
linktitle: Перечислить свойства
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по перечислению свойств документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/enumerate-properties/
---

В этом руководстве мы познакомим вас с исходным кодом C# для перечисления свойств документа с помощью Aspose.Words для .NET. Эта функция позволяет получить доступ к встроенным и настраиваемым свойствам документа.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом этапе мы загрузим документ Word, свойства которого мы хотим вывести. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3. Перечисление свойств

Теперь перечислим свойства документа, как встроенные, так и настраиваемые. Используйте следующий код:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Этот код отображает имя документа, а затем перечисляет встроенные и настраиваемые свойства с их именем и значением.

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

 Обязательно укажите правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как перечислять свойства документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы можете легко получить доступ и просмотреть свойства своих собственных документов.

