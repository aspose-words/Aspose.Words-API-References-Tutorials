---
title: Номер списка перезапуска
linktitle: Номер списка перезапуска
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как сбросить номер списка в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-list/restart-list-number/
---
В этом пошаговом руководстве мы покажем вам, как сбросить номер списка в документе Word с помощью Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы еще этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Создание документа и генератора документов

Сначала создайте новый документ и связанный с ним генератор документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2: Создание и настройка первого списка

Далее создайте список на основе существующего шаблона, затем настройте его уровни:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Шаг 3: Добавление элементов в первый список

Используйте конструктор документов, чтобы добавить элементы в первый список и удалить номера списка:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Шаг 4: Создание и настройка второго списка

Чтобы повторно использовать первый список путем сброса номера, создайте копию исходного макета списка:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

При необходимости вы также можете внести дополнительные изменения во второй список.

## Шаг 5: Добавление элементов во второй список

Снова используйте конструктор документов, чтобы добавить элементы во второй список и удалить номера списка:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Шаг 6: Сохраните измененный документ

Наконец, сохраните измененный документ:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Так ! Вы успешно сбросили номер списка в документе Word, используя Aspose.Words для .NET.

### Пример исходного кода для сброса номера списка

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте список на основе шаблона.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Чтобы повторно использовать первый список, нам нужно перезапустить нумерацию, создав копию исходного форматирования списка.
List list2 = doc.Lists.AddCopy(list1);

//Мы можем изменить новый список любым способом, в том числе установить новый стартовый номер.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Часто задаваемые вопросы

#### Q: Как перезапустить нумерацию списка в Aspose.Words?

 О: Чтобы перезапустить нумерацию списка в Aspose.Words, вы можете использовать`ListRestartAtNumber` метод`List` сорт. Этот метод позволяет вам установить новое значение набора, с которого список должен быть перезапущен. Например, вы можете использовать`list.ListRestartAtNumber(1)` возобновить нумерацию с 1.

#### В: Можно ли настроить префикс и суффикс нумерации перезапускаемых списков в Aspose.Words?

 О: Да, вы можете настроить префикс и суффикс нумерации перезапущенных списков в Aspose.Words.`ListLevel` класс предлагает такие свойства, как`ListLevel.NumberPrefix` и`ListLevel.NumberSuffix` которые позволяют указать префикс и суффикс для каждого уровня в списке. Вы можете использовать эти свойства для настройки префикса и суффикса по мере необходимости.

#### Q: Как я могу указать конкретное значение нумерации, с которого должен быть перезапущен список?

 A: Чтобы указать конкретное числовое значение, с которого должен перезапускаться список, вы можете использовать`ListRestartAtNumber`метод, передающий желаемое значение в качестве аргумента. Например, чтобы начать нумерацию с 5, вы можете использовать`list.ListRestartAtNumber(5)`.

#### В: Можно ли перезапустить нумерацию многоуровневых списков в Aspose.Words?

 О: Да, Aspose.Words поддерживает повторную нумерацию нескольких уровней списка. Вы можете применить`ListRestartAtNumber` метод на каждом уровне списка для индивидуального перезапуска нумерации. Например, вы можете использовать`list.Levels[0].ListRestartAtNumber(1)` чтобы перезапустить первый уровень списка с 1, и`list.Levels[1].ListRestartAtNumber(1)` чтобы перезапустить список второго уровня, начиная с 1, и так далее.



