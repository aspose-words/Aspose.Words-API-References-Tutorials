---
title: Получить плавающую позицию таблицы
linktitle: Получить плавающую позицию таблицы
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить положение плавающих таблиц в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/get-floating-table-position/
---

В этом уроке мы узнаем, как получить позицию плавающей таблицы в документе Word, используя Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программно получить свойства позиционирования плавающей таблицы в ваших документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа и доступ к таблицам
Чтобы запустить Word Processing с таблицами, нам нужно загрузить содержащий их документ и получить к ним доступ. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов. Также убедитесь, что документ содержит плавающие таблицы.

## Шаг 3: Получение свойств позиционирования плавающей таблицы
Далее мы пройдемся по всем таблицам в документе и получим свойства позиционирования плавающей таблицы. Используйте следующий код:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Если массив имеет плавающий тип, то выведите его свойства позиционирования.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Здесь мы используем`foreach` loop для перебора всех массивов в документе. Мы проверяем, является ли массив типом с плавающей запятой, проверяя`TextWrapping` свойство. Если это так, мы печатаем свойства позиционирования таблицы, такие как горизонтальная привязка, вертикальная привязка, абсолютные расстояния по горизонтали и вертикали, разрешение перекрытия, абсолютное расстояние по горизонтали и относительное выравнивание по вертикали.
 
### Пример исходного кода для получения позиции плавающей таблицы с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Если таблица плавающего типа, то выведите ее свойства позиционирования.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Заключение
В этом руководстве мы узнали, как получить позицию плавающей таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете программно получить свойства позиционирования плавающих таблиц в документах Word. Эта функция позволяет анализировать плавающие таблицы и управлять ими в соответствии с вашими конкретными потребностями.