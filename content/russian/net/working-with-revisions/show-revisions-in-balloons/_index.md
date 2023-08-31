---
title: Показывать изменения в выносках
linktitle: Показывать изменения в выносках
second_title: API обработки документов Aspose.Words
description: Покажите изменения в выносках с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/show-revisions-in-balloons/
---

В этом пошаговом руководстве мы покажем вам, как отображать изменения в выносках в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего изменения.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Настройте параметры просмотра обзора

Мы настроим параметры отображения, чтобы изменения были видны в выносках.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Шаг 3. Сохраните документ в формате PDF.

Наконец, мы сохраним документ в формате PDF, в котором изменения будут показаны в выносках.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Форматы вывода Markdown

Вывод может быть отформатирован в уценке для улучшения читаемости. Например :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Пример исходного кода для отображения ревизий в выносках с использованием Aspose.Words для .NET

Вот полный исходный код для отображения изменений в выносках в документе с использованием Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Визуализаторы вставляют ревизии в текст, удаляют и форматируют ревизии в выносках.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Отображает полосы изменений в правой части страницы.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Заключение

В этом уроке мы узнали, как отображать версии в виде выносок в документе Word с помощью Aspose.Words для .NET. Используя соответствующие параметры отображения, мы смогли сделать изменения видимыми в пузырьках с полосами исправлений с правой стороны. Aspose.Words for .NET предлагает множество мощных функций для управления документами Word, включая управление версиями. Теперь вы можете использовать эти знания для отображения изменений в выносках в ваших собственных документах Word, используя Aspose.Words для .NET.


### Часто задаваемые вопросы

#### Вопрос: Как загрузить документ в Aspose.Words для .NET?

 А: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Вопрос: Как отображать версии в виде всплывающих окон с помощью Aspose.Words for .NET?

 А: Используйте`ShowInBalloons` собственность`RevisionOptions` объект для настройки отображения ревизий в выносках. Вы можете установить это свойство на`ShowInBalloons.FormatAndDelete` для отображения редакций в выносках с удалением и форматированием редакций.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### Вопрос: Как сохранить документ в формате PDF с помощью Aspose.Words for .NET?

 А: Используйте`Save` метод`Document` объект для сохранения документа в формате PDF. Вы должны указать полный путь назначения с расширением «.pdf».

```csharp
doc.Save("path/to/destination/document.pdf");
```