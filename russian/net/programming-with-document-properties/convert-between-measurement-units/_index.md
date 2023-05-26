---
title: Преобразование между единицами измерения
linktitle: Преобразование между единицами измерения
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по преобразованию единиц измерения в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/convert-between-measurement-units/
---

В этом руководстве мы познакомим вас с исходным кодом C# для преобразования единиц измерения с помощью Aspose.Words для .NET. Эта функция позволяет указывать поля, расстояние между верхним и нижним колонтитулами и т. д. в разных единицах измерения.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в своей любимой среде IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2: Создание документа и конструктора

На этом шаге мы создадим новый документ и инициализируем конструктор. Используйте следующий код:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Настройте единицы измерения

Теперь мы переведем значения полей, расстояний верхнего и нижнего колонтитула и т. д. в разные единицы измерения. Используйте следующий код, чтобы указать значения в определенных единицах измерения:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Этот код использует`ConvertUtil` класс Aspose.Words для преобразования указанных значений в дюймы (`InchToPoint` ). Вы также можете использовать другие методы преобразования, доступные в`ConvertUtil` класс для преобразования значений в другие единицы измерения.

### Пример исходного кода для преобразования между единицами измерения с использованием Aspose.Words для .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	PageSetup pageSetup = builder.PageSetup;
	pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
	pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
	pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
	pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
  
```

Теперь вы узнали, как преобразовывать единицы измерения при указании полей, расстояний между верхним и нижним колонтитулами и т. д. в документе с использованием Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете легко указывать значения в нужных единицах измерения в своих собственных документах.