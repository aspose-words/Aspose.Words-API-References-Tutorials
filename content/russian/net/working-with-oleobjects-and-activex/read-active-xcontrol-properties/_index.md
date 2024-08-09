---
title: Чтение активных свойств XControl из файла Word
linktitle: Чтение активных свойств XControl из файла Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как читать свойства элемента управления ActiveX из файлов Word с помощью Aspose.Words для .NET, в пошаговом руководстве. Совершенствуйте свои навыки автоматизации документов.
type: docs
weight: 10
url: /ru/net/working-with-oleobjects-and-activex/read-active-xcontrol-properties/
---
## Введение

В современную цифровую эпоху автоматизация является ключом к повышению производительности. Если вы работаете с документами Word, содержащими элементы управления ActiveX, вам может потребоваться прочитать их свойства для различных целей. Элементы управления ActiveX, такие как флажки и кнопки, могут содержать важные данные. Используя Aspose.Words для .NET, вы можете эффективно извлекать эти данные и манипулировать ими программно.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующее:

1.  Библиотека Aspose.Words для .NET: ее можно загрузить с сайта[здесь](https://releases.aspose.com/words/net/).
2. Visual Studio или любая другая среда разработки C#: для написания и выполнения кода.
3. Документ Word с элементами управления ActiveX: например, «ActiveX elements.docx».
4. Базовые знания C#: Для дальнейшего обучения необходимо знание программирования на C#.

## Импортировать пространства имен

Сначала давайте импортируем необходимые пространства имен для работы с Aspose.Words for .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Drawing.Ole;
using System;
```

## Шаг 1. Загрузите документ Word

Для начала вам необходимо загрузить документ Word, содержащий элементы управления ActiveX.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "ActiveX controls.docx");
```

## Шаг 2. Инициализируйте строку для хранения свойств

Затем инициализируйте пустую строку для хранения свойств элементов управления ActiveX.

```csharp
string properties = "";
```

## Шаг 3. Перебор фигур в документе

Нам нужно перебрать все фигуры в документе, чтобы найти элементы управления ActiveX.

```csharp
foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    if (shape.OleFormat is null) continue;
    
    OleControl oleControl = shape.OleFormat.OleControl;
    if (oleControl.IsForms2OleControl)
    {
        // Обработка элемента ActiveX
    }
}
```

## Шаг 4. Извлечение свойств из элементов управления ActiveX

Внутри цикла проверьте, является ли элемент управления Forms2OleControl. Если это так, приведите его и извлеките свойства.

```csharp
Forms2OleControl checkBox = (Forms2OleControl) oleControl;
properties += "\nCaption: " + checkBox.Caption;
properties += "\nValue: " + checkBox.Value;
properties += "\nEnabled: " + checkBox.Enabled;
properties += "\nType: " + checkBox.Type;

if (checkBox.ChildNodes != null)
{
    properties += "\nChildNodes: " + checkBox.ChildNodes;
}

properties += "\n";
```

## Шаг 5. Подсчитайте общее количество элементов управления ActiveX

После обхода всех фигур подсчитайте общее количество найденных элементов ActiveX.

```csharp
properties += "\nTotal ActiveX Controls found: " + doc.GetChildNodes(NodeType.Shape, true).Count;
```

## Шаг 6: Отобразите свойства

Наконец, выведите извлеченные свойства на консоль.

```csharp
Console.WriteLine("\n" + properties);
```

## Заключение

И вот оно! Вы успешно научились читать свойства элемента управления ActiveX из документа Word с помощью Aspose.Words для .NET. В этом руководстве рассматривается загрузка документа, перебор фигур и извлечение свойств из элементов управления ActiveX. Выполнив эти шаги, вы сможете автоматизировать извлечение важных данных из документов Word, повысив эффективность рабочего процесса.

## Часто задаваемые вопросы

### Что такое элементы управления ActiveX в документах Word?
Элементы управления ActiveX — это интерактивные объекты, встроенные в документы Word, такие как флажки, кнопки и текстовые поля, используемые для создания форм и автоматизации задач.

### Могу ли я изменить свойства элементов управления ActiveX с помощью Aspose.Words для .NET?
Да, Aspose.Words for .NET позволяет программно изменять свойства элементов управления ActiveX.

### Можно ли использовать Aspose.Words для .NET бесплатно?
 Aspose.Words for .NET предлагает бесплатную пробную версию, но для дальнейшего использования вам необходимо приобрести лицензию. Вы можете получить бесплатную пробную версию[здесь](https://releases.aspose.com/).

### Могу ли я использовать Aspose.Words для .NET с другими языками .NET, кроме C#?
Да, Aspose.Words for .NET можно использовать с любым языком .NET, включая VB.NET и F#.

### Где я могу найти дополнительную документацию по Aspose.Words для .NET?
 Вы можете найти подробную документацию[здесь](https://reference.aspose.com/words/net/).