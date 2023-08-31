---
title: Особенности открытого типа
linktitle: Особенности открытого типа
second_title: API обработки документов Aspose.Words
description: Узнайте, как включить и использовать функции открытого типа в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/enable-opentype-features/open-type-features/
---

В этом подробном руководстве вы узнаете, как включить и использовать функции открытого типа в Aspose.Words для .NET. Мы проведем вас через этот процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете работать с функциями Open Type в своих документах Word.

## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- Библиотека Aspose.Words for .NET, установленная в вашей системе.

## Шаг 1. Загрузите документ
Для начала загрузите документ, используя класс Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## Шаг 2. Включите функции открытого типа
Чтобы включить функции открытого типа, установите для свойства TextShaperFactory класса LayoutOptions экземпляр нужной фабрики формирователя текста. В этом примере мы используем HarfBuzzTextShaperFactory:

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## Шаг 3. Сохраните документ
После включения функций открытого типа сохраните документ в нужном выходном формате, например PDF:

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Пример исходного кода для функций открытого типа с использованием Aspose.Words для .NET
Вот полный исходный код для использования функций открытого типа в Aspose.Words для .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## Заключение
Поздравляем! Вы успешно научились включать и использовать функции открытого типа в Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, вы теперь можете работать с функциями Open Type в своих документах Word.

Функции Open Type предлагают расширенные возможности типографики и формирования текста, что позволяет создавать визуально привлекательные и профессионально выглядящие документы. Поэкспериментируйте с различными фабриками формирователей текста и изучите возможности функций Open Type в своих проектах.

### Часто задаваемые вопросы

#### Вопрос: Как включить функции OpenType в Aspose.Words для .NET?

О: Чтобы включить функции OpenType в Aspose.Words для .NET, вам необходимо выполнить шаги, упомянутые в руководстве.

#### Вопрос: Какие функции OpenType поддерживаются в Aspose.Words для .NET?

О: Aspose.Words for .NET поддерживает несколько функций OpenType, таких как лигатуры, варианты глифов, контекстные замены и многое другое.

#### Вопрос: Как проверить, поддерживается ли функция OpenType для определенного шрифта?

О: Вы можете проверить, поддерживается ли функция OpenType в конкретном шрифте, используя`Font.OpenTypeFeatures` метод в Aspose.Words для .NET.

#### Вопрос: Какие еще функции форматирования текста поддерживает Aspose.Words for .NET?

О: Помимо функций OpenType, Aspose.Words for .NET также поддерживает другие функции форматирования текста, такие как форматирование абзацев, создание таблиц, добавление изображений и т. д.

#### Вопрос: Могу ли я использовать функции OpenType во всех версиях Aspose.Words для .NET?

О: Функции OpenType поддерживаются в более новых версиях Aspose.Words для .NET. Чтобы воспользоваться этими функциями, убедитесь, что вы используете совместимую версию.