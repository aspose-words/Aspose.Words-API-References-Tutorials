---
title: Используйте символ пробела на уровне для отступа списка
linktitle: Используйте символ пробела на уровне для отступа списка
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по использованию символа пробела на каждом уровне для отступа списка в Aspose.Words для .NET. С легкостью создавайте хорошо структурированные документы Word.
type: docs
weight: 10
url: /ru/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET — это мощная библиотека для создания, редактирования и управления документами Word в приложении C#. Среди функций, предлагаемых Aspose.Words, — возможность использования одного пробела на уровне для отступа списков. В этом руководстве мы покажем вам, как использовать исходный код C# Aspose.Words для .NET для реализации этой функциональности.

## Понимание библиотеки Aspose.Words

Прежде чем погрузиться в код, важно понять библиотеку Aspose.Words для .NET. Aspose.Words — популярная библиотека, которая делает работу с документами Word простой и эффективной. Он предлагает широкий спектр функций для создания, изменения и управления документами Word, включая управление списками и отступами.

## Создание документа и добавление содержимого

Первый шаг — создать новый документ и добавить в него содержимое. Используйте класс Document для создания нового экземпляра документа. Затем используйте класс DocumentBuilder, чтобы добавить текст и создать список с несколькими уровнями отступов. Вот пример:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте список с тремя уровнями отступа
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

В этом примере мы создаем новый документ и используем DocumentBuilder для добавления текста и создания списка с тремя уровнями отступов. Мы добавили в список три элемента, каждый из которых имеет отступ на дополнительный уровень.

## Использование одного пробела на уровень для отступа списка

После добавления контента мы можем настроить отступы списков, используя один символ пробела на уровень. Для этого мы используем класс TxtSaveOptions и устанавливаем для свойства ListIndentation.Count число уровней отступа, а для свойства ListIndentation.Character — используемый символ пробела. Вот как:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

В этом примере мы создаем экземпляр TxtSaveOptions и устанавливаем для свойства ListIndentation.Count значение 3, чтобы указать, что в списке есть три уровня отступа. Мы также устанавливаем для свойства ListIndentation.Character символ пробела (' '), который мы хотим использовать для отступа.

### Пример исходного кода для функции «Использовать один символ пробела на уровне для отступа списка» с Aspose.Words для .NET

Вот полный пример исходного кода для функции «Использовать один символ пробела на уровне для отступа списка» с Aspose.Words для .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Путь к вашему каталогу документов
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Создайте документ и добавьте содержимое
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Создайте список с тремя уровнями отступа
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Используйте один пробел на уровень для отступа списка
             TxtSaveOptions saveOptions = new TxtSaveOptions();
             saveOptions.ListIndentation.Count = 3;
             saveOptions.ListIndentation.Character = ' ';

             // Сохраните документ с указанными параметрами
             doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
         }
     }
}

```

## Заключение

В этом руководстве мы объяснили, как использовать Aspose.Words для .NET для применения функции «Использовать один пробел на уровне для отступа списка». Следуя приведенным шагам и используя предоставленный исходный код C#, вы можете легко настроить отступ списков в документах Word, используя один символ пробела на уровень. Aspose.Words предлагает огромную гибкость и мощность для работы с форматированием текста и управлением списками, позволяя вам создавать хорошо структурированные документы в вашем приложении C#.