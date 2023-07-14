---
title: Укажите уровень списка
linktitle: Укажите уровень списка
second_title: API обработки документов Aspose.Words
description: Узнайте, как указать уровень списка в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-list/specify-list-level/
---

В этом пошаговом руководстве мы покажем вам, как указать уровень списка в документе Word с помощью Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы еще этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Создание документа и генератора документов

Сначала создайте новый документ и связанный с ним генератор документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Создание и применение нумерованного списка

Затем создайте нумерованный список на основе одного из шаблонов списков Microsoft Word и примените его к текущему абзацу в конструкторе документов:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Шаг 3: Спецификация уровня списка

 Используйте конструктор документов`ListLevelNumber` чтобы указать уровень списка и добавить текст в абзац:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Повторите эти шаги, чтобы указать уровни списка и добавить текст на каждом уровне.

## Шаг 4: Создание и применение маркированного списка

Вы также можете создать и применить маркированный список, используя один из шаблонов списков Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Шаг 5: Добавление текста в уровни маркированного списка

 Использовать`ListLevelNumber` еще раз, чтобы указать уровень маркированного списка и добавить текст:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Шаг 6: Прекратите форматирование списка

 Чтобы остановить форматирование списка, установите`null` к`List` свойство генератора документов:

```csharp
builder. ListFormat. List = null;
```

## Шаг 7: Сохранение измененного документа

Сохраните измененный документ:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Так ! Вы успешно указали уровень списка в документе Word, используя Aspose.Words для .NET.

### Пример исходного кода для указания уровня списка

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//Создайте нумерованный список на основе одного из шаблонов списка Microsoft Word.
// и примените его к текущему абзацу конструктора документов.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// В этом списке девять уровней, давайте попробуем их все.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Создайте маркированный список на основе одного из шаблонов списка Microsoft Word.
// и примените его к текущему абзацу конструктора документов.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Это способ остановить форматирование списка.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Часто задаваемые вопросы

#### Q: Как указать уровень списка в Aspose.Words?

 A: Чтобы указать уровень списка в Aspose.Words, вам нужно создать экземпляр`List` class и дайте ему нумерованный список. Затем вы можете использовать`Paragraph.ListFormat.ListLevelNumber` свойство, чтобы указать уровень каждого элемента списка. Вы можете связать этот список с разделом вашего документа, чтобы элементы списка имели нужный уровень.

#### В: Можно ли изменить формат нумерации элементов списка в Aspose.Words?

 О: Да, вы можете изменить формат нумерации элементов списка в Aspose.Words.`ListLevel` класс предлагает несколько свойств для этого, таких как`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`и т. д. Эти свойства можно использовать для установки формата нумерации элементов списка, например арабских цифр, римских цифр, букв и т. д.

#### В: Могу ли я добавить дополнительные уровни в нумерованный список в Aspose.Words?

 О: Да, в пронумерованный список в Aspose.Words можно добавлять дополнительные уровни.`ListLevel` class позволяет вам установить свойства форматирования для каждого уровня списка. Вы можете установить такие параметры, как префикс, суффикс, выравнивание, отступ и т. д. Это позволяет создавать списки с несколькими уровнями иерархии.


