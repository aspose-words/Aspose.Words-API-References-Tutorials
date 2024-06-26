---
title: Группа разрыва линий азиатской типографии в документе Word
linktitle: Группа разрыва линий азиатской типографии в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать группу разрывов строк азиатской типографии в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-formatting/asian-typography-line-break-group/
---
В этом уроке мы покажем вам, как использовать группу разрывов строк азиатской типографии в функции документа Word с Aspose.Words для .NET. Выполните следующие действия, чтобы понять исходный код и применить изменения форматирования.

## Шаг 1: Загрузка документа

Для начала укажите каталог для ваших документов и загрузите документ, содержащий азиатскую типографику, в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Шаг 2: Настройка азиатской типографики

Теперь мы настроим настройки азиатской типографики для первого абзаца документа. Вот как:

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## Шаг 3. Сохраните документ.

 После вставки поля формы ввода текста сохраните документ в нужное место с помощью кнопки`Save` метод. Обязательно укажите правильный путь к файлу:

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### Пример исходного кода для группы разрыва строк азиатской типографии с использованием Aspose.Words для .NET

Вот полный исходный код функции разрыва строк азиатской типографии с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
С помощью этого кода вы сможете применить группу разрывов строк азиатской типографии, используя Aspose.Words для .NET.

## Заключение

 В этом уроке мы рассмотрели функцию «Группа разрыва строк азиатской типографии» в Aspose.Words для .NET. Настроив`FarEastLineBreakControl`, `WordWrap` , и`HangingPunctuation` свойства`ParagraphFormat`, мы смогли контролировать поведение разрыва строк для азиатской типографики в документе Word. Эта функция полезна для обработки азиатских символов и обеспечения правильных разрывов строк и переноса слов в документах со смешанным языковым содержанием.

### Часто задаваемые вопросы

#### Вопрос: Что такое функция «Группа разрыва строк азиатской типографии» в Aspose.Words для .NET?

О: Функция «Группа разрыва строк азиатской типографики» в Aspose.Words для .NET позволяет вам управлять поведением разрыва строк для азиатской типографики в документе Word. В частности, это влияет на то, как строки разбиваются и переносятся при работе с азиатскими символами в абзацах.

#### Вопрос: Как включить «Группу разрыва строк азиатской типографии» в Aspose.Words для .NET?

 О: Чтобы включить «Группу разрыва линий азиатской типографии», вам необходимо настроить`FarEastLineBreakControl`, `WordWrap` , и`HangingPunctuation` свойства`ParagraphFormat` для соответствующего параграфа(ов) в вашем документе. Параметр`FarEastLineBreakControl` к`false` Гарантирует, что азиатские символы обрабатываются аналогично латинским символам в отношении разрыва строки.`WordWrap` установлен в`true` Включает перенос слов для азиатской типографики и`HangingPunctuation` установлен в`false` Предотвращает зависание знаков препинания в азиатском тексте.

#### Вопрос: Могу ли я применить «Группу разрыва строк азиатской типографии» к определенным абзацам документа?

О: Да, вы можете применить настройки «Группа разрыва строк азиатского шрифта» к определенным абзацам в документе Word. В примере кода настройки применяются к первому абзацу документа. При необходимости вы можете настроить код так, чтобы он ориентировался на другие абзацы, получая к ним доступ через`Paragraphs` сбор соответствующего раздела(ов) в документе.