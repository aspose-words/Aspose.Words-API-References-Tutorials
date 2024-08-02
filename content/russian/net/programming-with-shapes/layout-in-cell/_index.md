---
title: Макет в ячейке
linktitle: Макет в ячейке
second_title: API обработки документов Aspose.Words
description: Узнайте, как настроить макет в ячейке с помощью Aspose.Words для .NET, с помощью этого подробного руководства. Идеально подходит для разработчиков, желающих настроить документы Word.
type: docs
weight: 10
url: /ru/net/programming-with-shapes/layout-in-cell/
---
## Введение

Если вы когда-нибудь хотели программно настроить расположение ячеек таблицы в документах Word, вы попали по адресу. Сегодня мы углубимся в то, как настроить макет в ячейке с помощью Aspose.Words для .NET. Мы рассмотрим практический пример, разбив его шаг за шагом, чтобы вы могли легко следовать ему.

## Предварительные условия

Прежде чем мы перейдем к коду, давайте убедимся, что у вас есть все необходимое:

1.  Aspose.Words for .NET: убедитесь, что у вас установлена библиотека Aspose.Words for .NET. Если у вас нет, вы можете[скачай это здесь](https://releases.aspose.com/words/net/).
2. Среда разработки: вам понадобится среда разработки, настроенная на .NET. Visual Studio — отличный выбор, если вам нужны рекомендации.
3. Базовые знания C#: Хотя я объясню каждый шаг, базовое понимание C# поможет вам легче следовать дальше.
4.  Каталог документов: подготовьте путь к каталогу, в котором вы будете сохранять свои документы. Мы будем называть это`YOUR DOCUMENT DIRECTORY`.

## Импортировать пространства имен

Для начала убедитесь, что вы импортируете необходимые пространства имен в свой проект:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Давайте разобьем процесс на управляемые этапы.

## Шаг 1. Создайте новый документ

 Сначала мы создадим новый документ Word и инициализируем его.`DocumentBuilder` объект, который поможет нам создать наш контент.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Создайте таблицу и установите формат строки

Мы начнем создавать таблицу и укажем высоту и правило высоты для строк.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Шаг 3. Вставьте ячейки и заполните их содержимым

Далее мы выполняем цикл для вставки ячеек в таблицу. Для каждых 7 ячеек мы завершаем строку, чтобы создать новую.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Шаг 4. Добавьте фигуру водяного знака

 Теперь давайте добавим водяной знак в наш документ. Мы создадим`Shape` объект и установите его свойства.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Отобразите фигуру за пределами ячейки таблицы, если она будет помещена в ячейку.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Шаг 5. Настройте внешний вид водяного знака

Далее мы настроим внешний вид водяного знака, установив его свойства цвета и текста.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Шаг 6. Вставьте водяной знак в документ

Мы найдем последний запуск в документе и вставим водяной знак в это место.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Шаг 7. Оптимизация документа для Word 2010

Чтобы обеспечить совместимость, мы оптимизируем документ для Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Шаг 8: Сохраните документ

Наконец, мы сохраним наш документ в указанном каталоге.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Заключение

И вот оно! Вы успешно создали документ Word с настроенным макетом таблицы и добавили водяной знак с помощью Aspose.Words для .NET. Цель этого руководства — предоставить четкое пошаговое руководство, которое поможет вам понять каждую часть процесса. Благодаря этим навыкам вы теперь можете программно создавать более сложные и настраиваемые документы Word.

## Часто задаваемые вопросы

### Могу ли я использовать другой шрифт для текста водяного знака?
 Да, вы можете изменить шрифт, установив`watermark.TextPath.FontFamily` свойство к желаемому шрифту.

### Как настроить положение водяного знака?
 Вы можете изменить`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , и`VerticalAlignment` свойства для настройки положения водяного знака.

### Можно ли использовать изображение вместо текста для водяного знака?
 Абсолютно! Вы можете создать`Shape` с типом`ShapeType.Image` и установите его изображение с помощью`ImageData.SetImage` метод.

### Могу ли я создавать таблицы с разной высотой строк?
Да, вы можете установить разную высоту для каждой строки, изменив`RowFormat.Height` перед вставкой ячеек в эту строку.

### Как удалить водяной знак из документа?
 Вы можете удалить водяной знак, найдя его в коллекции фигур документа и вызвав метод`Remove` метод.