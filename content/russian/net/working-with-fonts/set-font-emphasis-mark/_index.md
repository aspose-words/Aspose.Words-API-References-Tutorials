---
title: Установить метку выделения шрифта
linktitle: Установить метку выделения шрифта
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить стиль выделения шрифта в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-font-emphasis-mark/
---

В этом уроке мы покажем вам, как установить стиль выделения шрифта в документе Word с помощью Aspose.Words для .NET. Выделение шрифта используется для выделения определенных слов или фраз в тексте.

## Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующие предметы:
- Знание языка программирования C# на рабочем уровне
- Библиотека Aspose.Words для .NET, установленная в вашем проекте

## Шаг 1: Определите каталог документов
 Начните с установки пути к каталогу, где находится ваш документ Word. Заменять`"YOUR DOCUMENT DIRECTORY"` в коде с соответствующим путем.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создайте и настройте документ
 Создайте экземпляр`Document` класс и связанный с ним`DocumentBuilder` для создания содержимого документа. Использовать`Font.EmphasisMark` свойство, чтобы установить стиль акцента шрифта на`EmphasisMark.UnderSolidCircle` . Затем используйте`Write` и`Writeln` методы`DocumentBuilder` чтобы добавить текст с указанным выделением шрифта.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Шаг 3: Сохраните документ
 Сохраните документ с помощью`Save` метод`Document` с соответствующим путем и именем файла.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Пример исходного кода для установки метки выделения шрифта с использованием Aspose.Words для .NET 

```csharp
//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Заключение
В этом руководстве вы узнали, как установить стиль выделения шрифта в документе Word с помощью Aspose.Words для .NET. Поэкспериментируйте с различными стилями выделения и используйте эту функцию, чтобы выделять слова или фразы в документах.

### Часто задаваемые вопросы

#### В: Как добавить знаки ударения к определенному шрифту в документе Word с помощью Aspose.Words?

О: Чтобы добавить знаки ударения к определенному шрифту в документе Word с помощью Aspose.Words, вы можете использовать API, чтобы перейти к нужному шрифту и применить соответствующие знаки ударения. Это добавит знаки ударения к тексту с выбранным шрифтом.

#### В: Можно ли изменить стиль знаков ударения в документе Word с помощью Aspose.Words?

О: Да, с помощью Aspose.Words вы можете изменить стиль знаков ударения в документе Word. API позволяет настроить свойства стиля, такие как цвет, размер, тип линии и т. д., чтобы настроить внешний вид акцентных знаков.

#### В: Как удалить все знаки ударения из документа Word с помощью Aspose.Words?

О: Чтобы удалить все знаки ударения из документа Word с помощью Aspose.Words, вы можете использовать API для просмотра документа, обнаружения существующих знаков ударения и удаления их с помощью соответствующих методов. Это удалит все знаки выделения из документа.

#### В: Можно ли добавить знаки ударения к определенной части текста в документе Word?

О: Да, вы можете добавить знаки ударения к определенной части текста в документе Word с помощью Aspose.Words. Вы можете выбрать нужный диапазон текста с помощью API и добавить соответствующие метки выделения в эту часть текста.

#### В: Можно ли настроить акцентные знаки в соответствии с моими потребностями?

О: Да, знаки ударения можно настроить в соответствии с вашими потребностями с помощью Aspose.Words. Вы можете настроить свойства стиля акцентных знаков, такие как цвет, размер, тип линии и т. д., в соответствии со своими предпочтениями форматирования.