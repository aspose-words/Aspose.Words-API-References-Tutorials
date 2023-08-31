---
title: Плавающее положение стола
linktitle: Плавающее положение стола
second_title: API обработки документов Aspose.Words
description: Узнайте, как расположить таблицу в плавающем положении в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-tables/floating-table-position/
---

В этом уроке мы узнаем, как использовать Aspose.Words для .NET для размещения таблицы в плавающей позиции в документе Word. Мы будем следовать пошаговому руководству, чтобы понять код и реализовать эту функцию. В конце этого руководства вы сможете программно управлять положением и выравниванием плавающих таблиц в документах Word.

## Шаг 1: Настройка проекта
1. Запустите Visual Studio и создайте новый проект C#.
2. Добавьте ссылку на библиотеку Aspose.Words для .NET.

## Шаг 2: Загрузка документа и доступ к таблице
Чтобы запустить Word Processing с таблицей, нам нужно загрузить содержащий ее документ и получить к нему доступ. Следуй этим шагам:

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Доступ к массиву
Table table = doc.FirstSection.Body.Tables[0];
```

Обязательно замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на фактический путь к каталогу ваших документов. Кроме того, убедитесь, что документ содержит таблицу, которая будет располагаться в плавающем положении.

## Шаг 3: Размещение плавающей доски
Далее мы поместим таблицу в плавающую позицию, используя свойства, предоставляемые Aspose.Words для .NET. Используйте следующий код:

```csharp
// Позиционирование плавающего стола
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Здесь мы используем`AbsoluteHorizontalDistance` свойство для установки абсолютного горизонтального расстояния таблицы от левого края страницы. Мы также используем`RelativeVerticalAlignment` свойство, чтобы задать относительное вертикальное выравнивание таблицы относительно окружающего содержимого.

## Шаг 4: Сохранение измененного документа
Наконец, нам нужно сохранить измененный документ с таблицей, расположенной в плавающем положении. Используйте следующий код:

```csharp
// Сохраните измененный документ
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Обязательно укажите правильный путь и имя файла для выходного документа.

### Пример исходного кода для позиции плавающей таблицы с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Заключение
В этом руководстве мы узнали, как расположить таблицу в плавающем положении в документе Word с помощью Aspose.Words для .NET. Следуя этому пошаговому руководству и реализуя предоставленный код C#, вы можете программно управлять положением и выравниванием плавающих таблиц в документах Word.