---
title: Получить плавающую позицию стола
linktitle: Получить плавающую позицию стола
second_title: API обработки документов Aspose.Words
description: Узнайте, как получить положение плавающих таблиц в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/get-floating-table-position/
---

В этом уроке мы узнаем, как получить положение плавающей таблицы в документе Word с помощью Aspose.Words для .NET. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программным способом получить свойства позиционирования плавающей таблицы в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2. Загрузка документа и доступ к таблицам
Чтобы запустить обработку слов с таблицами, нам нужно загрузить документ, который их содержит, и получить к ним доступ. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» фактическим путем к каталогу ваших документов. Также убедитесь, что документ содержит плавающие таблицы.

## Шаг 3. Получение свойств позиционирования плавающей таблицы
Далее мы пройдемся по всем таблицам в документе и получим свойства позиционирования плавающей таблицы. Используйте следующий код:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Если массив имеет плавающий тип, выведите его свойства позиционирования.
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

 Здесь мы используем`foreach` цикл для перебора всех массивов в документе. Мы проверяем, является ли массив типом float, проверяя`TextWrapping` свойство. Если это так, мы печатаем свойства позиционирования таблицы, такие как горизонтальная привязка, вертикальная привязка, абсолютные горизонтальные и вертикальные расстояния, разрешение перекрытия, абсолютное горизонтальное расстояние и относительное вертикальное выравнивание.
 
### Пример исходного кода для получения позиции плавающей таблицы с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Если таблица имеет плавающий тип, распечатайте ее свойства позиционирования.
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
В этом уроке мы узнали, как получить положение плавающей таблицы в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализовав предоставленный код C#, вы можете программно получить свойства позиционирования плавающих таблиц в документах Word. Эта функция позволяет анализировать плавающие таблицы и манипулировать ими в соответствии с вашими конкретными потребностями.