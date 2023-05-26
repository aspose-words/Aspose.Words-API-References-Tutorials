---
title: Получить переменные
linktitle: Получить переменные
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по извлечению переменных документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/get-variables/
---

В этом руководстве мы познакомим вас с исходным кодом C# для извлечения переменных из документа с помощью Aspose.Words для .NET. Эта функция позволяет вам получить доступ к переменным, определенным в документе.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Загрузка документа

На этом шаге мы загрузим документ Word, из которого мы хотим получить переменные. Используйте следующий код для загрузки документа:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Заменять`"YOUR DOCUMENTS DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

## Шаг 3: Получение переменных

Теперь мы получим переменные, определенные в документе. Используйте следующий код:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

Этот код перебирает каждую пару ключ-значение в переменных документа и извлекает имя и значение каждой переменной. Затем переменные объединяются для отображения информации для каждой переменной.

### Пример исходного кода для получения переменных с использованием Aspose.Words для .NET

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

 Не забудьте указать правильный путь к документу в`dataDir` переменная.

Теперь вы узнали, как извлекать переменные из документа с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете легко получать доступ и просматривать переменные из ваших собственных документов.