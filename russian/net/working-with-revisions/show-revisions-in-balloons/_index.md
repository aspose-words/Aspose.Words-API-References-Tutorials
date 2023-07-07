---
title: Показать изменения в выносках
linktitle: Показать изменения в выносках
second_title: Справочник по API Aspose.Words для .NET
description: Показывайте исправления во всплывающих подсказках с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-revisions/show-revisions-in-balloons/
---

В этом пошаговом руководстве мы покажем вам, как отображать исправления во всплывающих подсказках в документе Word с помощью Aspose.Words для .NET. Мы предоставим вам полный исходный код и покажем, как форматировать выходные данные уценки.

## Шаг 1: Загрузка документа

Первым шагом является загрузка документа, содержащего исправления.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Шаг 2. Настройте параметры показа обзоров

Мы настроим параметры показа, чтобы изменения отображались во всплывающих подсказках.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## Шаг 3: Сохраните документ в формате PDF

Наконец, мы сохраним документ в формате PDF с исправлениями, показанными во всплывающих подсказках.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Выходные форматы уценки

Вывод может быть отформатирован в уценке для улучшения читаемости. Например :

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### Пример исходного кода для Show Revisions In Balloons с использованием Aspose.Words для .NET

Вот полный исходный код для отображения изменений в выносках в документе с использованием Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

// Визуализирует встроенные исправления, удаляет и форматирует исправления во всплывающих подсказках.
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
// Отображает полосы изменений в правой части страницы.
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Заключение

В этом уроке мы узнали, как отображать исправления во всплывающих подсказках в документе Word с помощью Aspose.Words для .NET. Используя соответствующие параметры отображения, мы смогли сделать исправления видимыми в пузырьках с полосами изменений с правой стороны. Aspose.Words для .NET предлагает множество мощных функций для работы с документами Word, включая управление версиями. Теперь вы можете использовать эти знания, чтобы отображать исправления во всплывающих подсказках в ваших собственных документах Word с помощью Aspose.Words для .NET.


### Часто задаваемые вопросы

#### В: Как загрузить документ в Aspose.Words для .NET?

 О: Используйте`Document` класс Aspose.Words для .NET для загрузки документа из файла. Вы можете указать полный путь к документу.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### В: Как отображать версии во всплывающих подсказках с помощью Aspose.Words для .NET?

 О: Используйте`ShowInBalloons` собственность`RevisionOptions` object для настройки отображения ревизий во всплывающих подсказках. Вы можете установить это свойство на`ShowInBalloons.FormatAndDelete` для отображения ревизий во всплывающих подсказках с исправлениями удаления и форматирования.

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### В: Как сохранить документ в формате PDF с помощью Aspose.Words для .NET?

 О: Используйте`Save` метод`Document` объекта для сохранения документа в формате PDF. Необходимо указать полный путь назначения с расширением «.pdf».

```csharp
doc.Save("path/to/destination/document.pdf");
```