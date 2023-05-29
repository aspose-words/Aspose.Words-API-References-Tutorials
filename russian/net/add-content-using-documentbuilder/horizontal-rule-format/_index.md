---
title: Формат горизонтального правила
linktitle: Формат горизонтального правила
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как форматировать горизонтальные линейки в документах Word с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/horizontal-rule-format/
---

В этом подробном примере вы узнаете, как отформатировать горизонтальную линейку в документе Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете настроить выравнивание, ширину, высоту, цвет и другие свойства горизонтальной линейки.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1. Создайте DocumentBuilder и вставьте горизонтальное правило
Для начала создайте объект DocumentBuilder и используйте метод InsertHorizontalRule для вставки горизонтальной линейки:

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## Шаг 2. Получите доступ к формату горизонтального правила
Затем откройте свойство HorizontalRuleFormat объекта Shape, чтобы получить параметры форматирования:

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## Шаг 3: Настройте параметры форматирования
Теперь вы можете настроить различные параметры форматирования горизонтальной линейки. Например, вы можете настроить выравнивание, ширину, высоту, цвет и затенение:

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## Шаг 4: Сохраните документ
После форматирования горизонтальной линейки сохраните документ в файл с помощью метода Save объекта Document:

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Пример исходного кода для формата горизонтального правила с использованием Aspose.Words для .NET
Вот полный исходный код для форматирования горизонтальной линейки с помощью Aspose.Words для .NET:

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

Не забудьте настроить код в соответствии с вашими конкретными требованиями и добавить в него дополнительные функции по мере необходимости.

## Заключение
Поздравляем! Вы успешно научились форматировать горизонтальную линейку в документе Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете настроить внешний вид горизонтальных линеек для улучшения визуального макета документа.

Поэкспериментируйте с различными параметрами форматирования, чтобы добиться желаемого стиля и эффекта для ваших горизонтальных линеек.
