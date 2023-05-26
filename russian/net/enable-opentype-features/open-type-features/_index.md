---
title: Особенности открытого типа
linktitle: Особенности открытого типа
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как включить и использовать функции Open Type в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/enable-opentype-features/open-type-features/
---

В этом всеобъемлющем руководстве вы узнаете, как включить и использовать функции Open Type в Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете работать с функциями Open Type в своих документах Word.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Загрузите документ
Для начала загрузите документ с помощью класса Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Шаг 2. Включите функции открытого типа
Чтобы включить функции открытого типа, задайте для свойства TextShaperFactory класса LayoutOptions экземпляр нужной фабрики формирователя текста. В этом примере мы используем HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Шаг 3: Сохраните документ
После включения функций Open Type сохраните документ в желаемом формате вывода, например PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Пример исходного кода для функций открытого типа с использованием Aspose.Words для .NET
Вот полный исходный код для использования функций Open Type в Aspose.Words для .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Заключение
Поздравляем! Вы успешно научились включать и использовать функции Open Type в Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете работать с функциями Open Type в своих документах Word.

Функции Open Type предлагают расширенные возможности типографики и оформления текста, позволяя создавать визуально привлекательные и профессионально выглядящие документы. Поэкспериментируйте с различными фабриками формирователя текста и изучите возможности функций Open Type в своих проектах.
