---
title: Преобразование между единицами измерения
linktitle: Преобразование между единицами измерения
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по преобразованию единиц измерения в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/convert-between-measurement-units/
---

В этом руководстве мы познакомим вас с исходным кодом C# для преобразования единиц измерения с помощью Aspose.Words для .NET. Эта функция позволяет вам указать поля, расстояния верхнего и нижнего колонтитула и т. д. в разных единицах измерения.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2. Создание документа и конструктора

На этом этапе мы создадим новый документ и инициализируем конструктор. Используйте следующий код:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Настройте единицы измерения

Теперь мы преобразуем значения полей, расстояний верхнего и нижнего колонтитула и т. д. в разных единицах измерения. Используйте следующий код, чтобы указать значения в конкретных единицах измерения:

```csharp
PageSetup pageSetup = builder.PageSetup;
pageSetup.TopMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.BottomMargin = ConvertUtil.InchToPoint(1.0);
pageSetup.LeftMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.RightMargin = ConvertUtil.InchToPoint(1.5);
pageSetup.HeaderDistance = ConvertUtil.InchToPoint(0.2);
pageSetup.FooterDistance = ConvertUtil.InchToPoint(0.2);
```

 Этот код использует`ConvertUtil` класс Aspose.Words для преобразования указанных значений в дюймы (`InchToPoint` ). Вы также можете использовать другие методы конвертации, доступные в`ConvertUtil` класс для преобразования значений в другие единицы измерения.

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

Теперь вы узнали, как конвертировать единицы измерения при указании полей, расстояний в верхнем и нижнем колонтитулах и т. д. в документе с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете легко указать значения в нужных единицах измерения в собственных документах.