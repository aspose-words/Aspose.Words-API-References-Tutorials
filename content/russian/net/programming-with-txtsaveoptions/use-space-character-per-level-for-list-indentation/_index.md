---
title: Используйте пробел на уровне для отступа списка
linktitle: Используйте пробел на уровне для отступа списка
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по использованию символа пробела на уровне для отступов списка в Aspose.Words для .NET. С легкостью создавайте хорошо структурированные документы Word.
type: docs
weight: 10
url: /ru/net/programming-with-txtsaveoptions/use-space-character-per-level-for-list-indentation/
---
Aspose.Words for .NET — это мощная библиотека для создания, редактирования и управления документами Word в приложении C#. Среди функций, предлагаемых Aspose.Words, — возможность использования одного пробела на уровне для отступов списков. В этом руководстве мы покажем вам, как использовать исходный код C# Aspose.Words для .NET для реализации этой функции.

## Понимание библиотеки Aspose.Words

Прежде чем углубиться в код, важно понять библиотеку Aspose.Words для .NET. Aspose.Words — популярная библиотека, которая делает обработку слов с документами Word простой и эффективной. Он предлагает широкий спектр функций для создания, изменения и управления документами Word, включая управление списками и отступами.

## Создание документа и добавление контента

Первым шагом является создание нового документа и добавление в него содержимого. Используйте класс Document для создания нового экземпляра документа. Затем используйте класс DocumentBuilder, чтобы добавить текст и создать список с несколькими уровнями отступов. Вот пример:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Создайте список с тремя уровнями идентификации.
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

В этом примере мы создаем новый документ и используем DocumentBuilder для добавления текста и создания списка с тремя уровнями отступов. Мы добавили в список три предмета, каждому из которых присвоен дополнительный уровень.

## Использование одного пробела на уровень для идентификации списка.

После добавления контента мы можем настроить отступы списков, используя один пробел на уровень. Для этого мы используем класс TxtSaveOptions и устанавливаем для свойства ListIndentation.Count количество уровней отступа, а для свойства ListIndentation.Character — используемый символ пробела. Вот как:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 3;
saveOptions.ListIndentation.Character = ' ';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
```

В этом примере мы создаем экземпляр TxtSaveOptions и устанавливаем для свойства ListIndentation.Count значение 3, чтобы указать, что в списке имеется три уровня отступов. Мы также устанавливаем для свойства ListIndentation.Character символ пробела (' '), который мы хотим использовать для отступа.

### Пример исходного кода функции «Использовать один пробел на уровне для отступов списка» в Aspose.Words для .NET

Вот полный пример исходного кода функции «Использовать один пробел на уровне для отступов списка» в Aspose.Words для .NET:

```csharp

using Aspose.Words;
using Aspose.Words.Saving;

namespace Example
{
     class Program
     {
         static void Main(string[] args)
         {
             // Путь к каталогу ваших документов
             string dataDir = "YOUR DOCUMENTS DIRECTORY";

             // Создайте документ и добавьте контент
             Document doc = new Document();
             DocumentBuilder builder = new DocumentBuilder(doc);

             // Создайте список с тремя уровнями идентификации.
             builder.ListFormat.ApplyNumberDefault();
             builder. Writen("Element 1");
             builder.ListFormat.ListIndent();
             builder. Writen("Element 2");
             builder.ListFormat.ListIndent();
             builder.Write("Element 3");

             // Используйте один пробел на уровень для идентификации списка.
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

В этом руководстве мы объяснили, как использовать Aspose.Words для .NET, чтобы применить функцию «Использовать один пробел на уровне для отступа списка». Следуя предоставленным инструкциям и используя предоставленный исходный код C#, вы можете легко настроить отступы списков в документах Word, используя один пробел на уровень. Aspose.Words предлагает огромную гибкость и мощность для обработки Word с форматированием текста и управлением списками, что позволяет вам создавать хорошо структурированные документы в вашем приложении C#.

### Часто задаваемые вопросы

#### Вопрос: Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это мощная библиотека для создания, редактирования и управления документами Word в приложении C#. Он предлагает множество функций для обработки слов с документами Word, включая возможность использовать одно пространство на уровень для отступов списков.

#### Вопрос: Как я могу использовать один пробел на уровень для отступов списка с помощью Aspose.Words для .NET?
Вы можете использовать одно пространство на уровень для отступов списка, выполнив следующие действия:

 Создайте новый документ, используя`Document` класс.

 Использовать`DocumentBuilder`класс для добавления содержимого в документ и создания списка с несколькими уровнями отступов.

 После того, как вы добавили контент и настроили отступ списка, используйте`TxtSaveOptions` класс и установите`ListIndentation.Count` свойства к количеству уровней отступов и`ListIndentation.Character` имущество на площади (`' '`) использовать.

 Сохраните документ с указанными параметрами, используя кнопку`Save` метод`Document` класс.

#### Вопрос: Поддерживает ли Aspose.Words другие символы для отступов списка?
Да, Aspose.Words поддерживает другие символы для отступов списков. Вы можете использовать символы без пробелов, такие как табуляция (`'\t'` ) или другие специальные символы, установив`ListIndentation.Character` свойство нужному персонажу.

#### Вопрос: Можно ли настроить количество мест на уровне для размещения списка?
 Да, вы можете настроить количество пробелов на уровне отступа списка, изменив значение параметра`ListIndentation.Count` недвижимость в`TxtSaveOptions` класс. Вы можете указать количество пробелов для каждого уровня отступа.

#### Вопрос: Какие еще функции предлагает Aspose.Words для управления списками?
Aspose.Words предлагает множество функций для управления списками в документах Word. Вы можете создавать нумерованные или маркированные списки, устанавливать уровни отступов, настраивать стиль списков, добавлять элементы списков и многое другое.