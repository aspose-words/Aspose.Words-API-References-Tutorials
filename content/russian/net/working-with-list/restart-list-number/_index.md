---
title: Номер списка перезапуска
linktitle: Номер списка перезапуска
second_title: API обработки документов Aspose.Words
description: Узнайте, как сбросить номер списка в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-list/restart-list-number/
---
В этом пошаговом руководстве мы покажем вам, как сбросить номер списка в документе Word с помощью Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем, как реализовать его в ваших собственных проектах.

 Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы еще этого не сделали, загрузите и установите библиотеку с сайта[Aspose.Releases]https://releases.aspose.com/words/net/.

## Шаг 1. Создание документа и генератора документов

Сначала создайте новый документ и связанный с ним генератор документов:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Создание и настройка первого списка

Затем создайте список на основе существующего шаблона, а затем настройте его уровни:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Шаг 3. Добавление элементов в первый список

Используйте конструктор документов, чтобы добавить элементы в первый список и удалить номера списка:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Шаг 4. Создание и настройка второго списка

Чтобы повторно использовать первый список путем сброса номера, создайте копию исходного макета списка:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

При необходимости вы также можете внести дополнительные изменения во второй список.

## Шаг 5. Добавление элементов во второй список

Снова используйте конструктор документов, чтобы добавить элементы во второй список и удалить номера списка:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Шаг 6. Сохраните измененный документ.

Наконец, сохраните измененный документ:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Так ! Вы успешно сбросили номер списка в документе Word с помощью Aspose.Words для .NET.

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

// Мы можем изменить новый список любым способом, включая установку нового стартового номера.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Часто задаваемые вопросы

#### Вопрос: Как перезапустить нумерацию списка в Aspose.Words?

 О: Чтобы перезапустить нумерацию списка в Aspose.Words, вы можете использовать команду`ListRestartAtNumber` метод`List` сорт. Этот метод позволяет установить новое значение набора, с которого следует перезапустить список. Например, вы можете использовать`list.ListRestartAtNumber(1)` чтобы возобновить нумерацию с 1.

#### Вопрос: Можно ли в Aspose.Words настроить префикс и суффикс нумерации перезапущенного списка?

 О: Да, вы можете настроить префикс и суффикс нумерации перезапущенного списка в Aspose.Words.`ListLevel` класс предлагает такие свойства, как`ListLevel.NumberPrefix` и`ListLevel.NumberSuffix` которые позволяют указать префикс и суффикс для каждого уровня в списке. Вы можете использовать эти свойства для настройки префикса и суффикса по мере необходимости.

#### Вопрос: Как указать конкретное значение нумерации, с которого следует перезапустить список?

О: Чтобы указать конкретное числовое значение, с которого следует перезапустить список, можно использовать команду`ListRestartAtNumber` метод, передающий желаемое значение в качестве аргумента. Например, чтобы перезапустить нумерацию с 5, вы можете использовать`list.ListRestartAtNumber(5)`.

#### Вопрос: Можно ли перезапустить многоуровневую нумерацию списков в Aspose.Words?

 О: Да, Aspose.Words поддерживает перезапуск нумерации нескольких уровней списка. Вы можете применить`ListRestartAtNumber` метод на каждом уровне списка для индивидуального перезапуска нумерации. Например, вы можете использовать`list.Levels[0].ListRestartAtNumber(1)` перезапустить первый уровень списка с 1 и`list.Levels[1].ListRestartAtNumber(1)` чтобы перезапустить список второго уровня, начиная с 1, и так далее.



