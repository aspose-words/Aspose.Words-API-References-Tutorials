---
title: Установить параметры концевой сноски
linktitle: Установить параметры концевой сноски
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить параметры концевых сносок в документах Word с помощью Aspose.Words для .NET. Пошаговое руководство с примером исходного кода.
type: docs
weight: 10
url: /ru/net/working-with-footnote-and-endnote/set-endnote-options/
---

В этом пошаговом руководстве мы расскажем вам, как использовать Aspose.Words для .NET для установки параметров концевых сносок в документе Word. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к исходному документу:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Шаг 2: Инициализация объекта DocumentBuilder

 Далее инициализируйте`DocumentBuilder` объект для выполнения операций над документом:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Добавление текста и концевой сноски

 Использовать`Write` метод`DocumentBuilder` объект для добавления текста в документ, а`InsertFootnote` способ вставки концевой сноски:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Шаг 4: Настройка параметров концевой сноски

 Доступ к`EndnoteOptions` свойство документа для изменения параметров концевой сноски. В этом примере мы устанавливаем правило перезапуска для перезапуска на каждой странице и положение в конце раздела:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Шаг 5: Сохранение документа

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Вот и все! Вы успешно установили параметры концевой сноски в документе Word, используя Aspose.Words для .NET.

### Пример исходного кода для установки параметров концевой сноски с использованием Aspose.Words для .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.

### Часто задаваемые вопросы

#### В: Как оформить концевые сноски в Aspose.Words?

 О: Чтобы оформить концевые сноски в Aspose.Words, вы можете использовать`EndnoteOptions` класс и`SeparatorNoteTextStyle` свойство. С помощью этого свойства вы можете указать стиль шрифта, размер, цвет и т. д. для концевых сносок.

#### В: Можно ли настроить нумерацию концевых сносок в документе?

 О: Да, можно настроить нумерацию концевых сносок в документе. Вы можете использовать`RestartRule` и`NumberStyle` свойства`EndnoteOptions` класс для определения конкретных правил перезапуска и стилей нумерации.

#### В: Как разместить концевые сноски в документе?

 О: Чтобы расположить концевые сноски в документе, вы можете использовать`Position`собственность`EndnoteOptions` сорт. Вы можете указать, должны ли концевые сноски размещаться внизу каждой страницы, в конце каждого раздела или в конце документа.

#### В: Могу ли я настроить формат нумерации концевых сносок?

 О: Да, вы можете настроить формат нумерации концевых сносок в Aspose.Words. Использовать`NumberFormat`собственность`EndnoteOptions` класс для установки желаемого формата, например, арабских цифр, римских цифр, букв и т. д.

#### В: Можно ли продолжить нумерацию концевых сносок между разделами документа?

 О: Да, можно продолжать нумерацию концевых сносок между разделами документа. Использовать`RestartRule`собственность`EndnoteOptions` класс и установите его на`RestartContinuous` чтобы нумерация продолжалась между разделами.