---
title: Получить позицию за столом
linktitle: Получить позицию за столом
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как получить позицию таблицы в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/get-table-position/
---

В этом уроке мы узнаем, как получить позицию таблицы в документе Word, используя Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программно получить свойства позиционирования таблиц в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа и доступ к таблице
Чтобы начать работу с таблицей, нам нужно загрузить содержащий ее документ и получить к нему доступ. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Загрузите документ
Document doc = new Document(dataDir + "Tables.docx");

// Доступ к массиву
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов. Также убедитесь, что документ содержит таблицу, положение которой вы хотите получить.

## Шаг 3: Получение свойств позиционирования массива
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

 Здесь мы используем условие, чтобы проверить, имеет ли массив тип float. Если да, то печатаем`RelativeHorizontalAlignment` и`RelativeVerticalAlignment` свойства, чтобы получить относительное горизонтальное и вертикальное выравнивание таблицы. В противном случае мы печатаем`Alignment` свойство, чтобы получить выравнивание массива.

### Пример исходного кода для получения позиции в таблице с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
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
В этом руководстве мы узнали, как получить позицию таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете программно получить свойства позиционирования таблиц в документах Word. Эта функция позволяет анализировать и манипулировать массивами в соответствии с их конкретными позициями.