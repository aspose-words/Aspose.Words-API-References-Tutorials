---
title: Номер списка перезапуска
linktitle: Номер списка перезапуска
second_title: API обработки документов Aspose.Words
description: Узнайте, как перезапустить номера списков в документах Word с помощью Aspose.Words для .NET. Это подробное руководство объемом 2000 слов охватывает все, что вам нужно знать, от настройки до расширенной настройки.
type: docs
weight: 10
url: /ru/net/working-with-list/restart-list-number/
---
## Введение

Хотите овладеть искусством манипулирования списками в документах Word с помощью Aspose.Words для .NET? Ну, вы в правильном месте! В этом уроке мы углубимся в перезапуск номеров списков — изящную функцию, которая поднимет ваши навыки автоматизации документов на новый уровень. Пристегнитесь, и начнем!

## Предварительные условия

Прежде чем мы перейдем к коду, давайте убедимся, что у вас есть все необходимое:

1.  Aspose.Words для .NET: вам необходимо установить Aspose.Words для .NET. Если вы еще не установили его, вы можете[скачай это здесь](https://releases.aspose.com/words/net/).
2. Среда разработки: убедитесь, что у вас есть подходящая среда разработки, например Visual Studio.
3. Базовые знания C#. Базовое понимание C# поможет вам следовать инструкциям.

## Импортировать пространства имен

Прежде всего, давайте импортируем необходимые пространства имен. Они имеют решающее значение для доступа к функциям Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Lists;
using System.Drawing;
```

Теперь давайте разобьем весь процесс на простые шаги. Мы рассмотрим все: от создания списка до возобновления его нумерации.

## Шаг 1. Настройте документ и конструктор

Прежде чем вы сможете начать манипулировать списками, вам понадобится документ и DocumentBuilder. DocumentBuilder — это ваш универсальный инструмент для добавления контента в документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Создайте и настройте свой первый список

Далее мы создадим список на основе шаблона и настроим его внешний вид. В этом примере мы используем арабский формат чисел с круглыми скобками.

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

Здесь мы установили красный цвет шрифта и выровняли текст по правому краю.

## Шаг 3. Добавьте элементы в свой первый список

 Когда ваш список готов, пришло время добавить несколько пунктов. DocumentBuilder's`ListFormat.List` Свойство помогает применить формат списка к тексту.

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Шаг 4. Перезапустите нумерацию списков.

Чтобы повторно использовать список и перезапустить его нумерацию, необходимо создать копию исходного списка. Это позволяет вам самостоятельно изменять новый список.

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

В этом примере новый список начинается с номера 10.

## Шаг 5. Добавьте элементы в новый список

Как и раньше, добавьте элементы в новый список. Это демонстрирует перезапуск списка с указанного номера.

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();
```

## Шаг 6. Сохраните документ

Наконец, сохраните документ в указанном каталоге.

```csharp
builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
```

## Заключение

Перезапуск номеров списков в документах Word с использованием Aspose.Words for .NET прост и невероятно полезен. Независимо от того, создаете ли вы отчеты, структурированные документы или просто хотите лучше контролировать свои списки, этот метод подойдет вам.

## Часто задаваемые вопросы

### Могу ли я использовать другие шаблоны списков, кроме NumberArabicParentesis?

Абсолютно! Aspose.Words предлагает различные шаблоны списков, такие как маркеры, буквы, римские цифры и многое другое. Вы можете выбрать тот, который лучше всего соответствует вашим потребностям.

### Как изменить уровень списка?

 Вы можете изменить уровень списка, изменив`ListLevels` свойство. Например,`list1.ListLevels[1]` будет относиться ко второму уровню списка.

### Могу ли я возобновить нумерацию с любого номера?

 Да, вы можете установить начальный номер в любое целое значение, используя`StartAt` свойство уровня списка.

### Возможно ли иметь разное форматирование для разных уровней списка?

Действительно! Каждый уровень списка может иметь свои собственные настройки форматирования, такие как шрифт, выравнивание и стиль нумерации.

### Что делать, если я хочу продолжить нумерацию из предыдущего списка, а не начинать заново?

Если вы хотите продолжить нумерацию, вам не нужно создавать копию списка. Просто продолжайте добавлять элементы в исходный список.


