---
title: Форматирование шрифта
linktitle: Форматирование шрифта
second_title: Справочник по API Aspose.Words для .NET
description: Из этого руководства вы узнаете, как отформатировать шрифт в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/font-formatting/
---

В этом руководстве мы расскажем, как выполнить форматирование шрифта в документе Word с помощью библиотеки Aspose.Words для .NET. Форматирование шрифта позволяет настраивать внешний вид текста, включая размер, жирность, цвет, шрифт, подчеркивание и т. д. Мы проведем вас шаг за шагом, чтобы помочь вам понять и реализовать код в вашем проекте .NET.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Определите каталог документов
 Во-первых, вам нужно указать путь к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создайте новый документ и генератор документов
 Далее мы создадим новый документ, создав экземпляр`Document` класс и конструктор документов, создав экземпляр`DocumentBuilder` сорт.

```csharp
// Создать новый документ
Document doc = new Document();

// Создать генератор документов
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Настройте форматирование шрифта.
 Теперь мы получим доступ к`Font` объект генератора документов и настроить свойства форматирования шрифта, такие как размер, жирность, цвет, шрифт, подчеркивание и т. д.

```csharp
// Доступ к шрифту
Font font = builder.Font;

// Настроить форматирование шрифта
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## Шаг 4: Добавьте текст в документ
Далее мы воспользуемся конструктором документов, чтобы добавить в документ форматированный текст.

```csharp
// Добавить текст в документ
builder.Write("Example text.");
```

## Шаг 5: Сохраните документ
Наконец, мы сохраним документ, содержащий форматирование шрифта.

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### Пример исходного кода для форматирования шрифта с использованием Aspose.Words для .NET 
```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## Заключение
В этом руководстве мы увидели, как выполнить форматирование шрифта в документе Word с помощью Aspose.Words для .NET. Форматирование шрифта позволяет настроить внешний вид текста в документах. Не стесняйтесь использовать эту функцию для создания привлекательных и профессиональных документов.