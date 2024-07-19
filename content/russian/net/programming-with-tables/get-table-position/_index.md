---
title: Получить позицию таблицы
linktitle: Получить позицию таблицы
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить положение таблицы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/get-table-position/
---

В этом уроке мы узнаем, как получить положение таблицы в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программным способом получить свойства позиционирования таблицы в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2. Загрузка документа и доступ к таблице.
Чтобы запустить обработку слов с таблицей, нам нужно загрузить документ, который ее содержит, и получить к нему доступ. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Tables.docx");

// Доступ к массиву
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим путем к каталогу ваших документов. Также убедитесь, что документ содержит таблицу, позицию которой вы хотите получить.

## Шаг 3. Получение свойств позиционирования массива
Далее мы проверим тип позиционирования массива и получим соответствующие свойства позиционирования. Используйте следующий код:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Здесь мы используем условие, чтобы проверить, имеет ли массив тип float. Если да, то мы распечатываем`RelativeHorizontalAlignment`и`RelativeVerticalAlignment` свойства, чтобы получить относительное горизонтальное и вертикальное выравнивание таблицы. В противном случае мы печатаем`Alignment` свойство для выравнивания массива.

### Пример исходного кода для получения позиции таблицы с помощью Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Заключение
В этом уроке мы узнали, как получить положение таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы можете программно получить свойства позиционирования таблицы в документах Word. Эта функция позволяет анализировать массивы и манипулировать ими в соответствии с их конкретными позициями.