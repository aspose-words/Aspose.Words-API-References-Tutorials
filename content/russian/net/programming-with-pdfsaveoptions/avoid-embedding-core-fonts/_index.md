---
title: Уменьшите размер PDF-файла, не встраивая основные шрифты
linktitle: Уменьшите размер PDF-файла, не встраивая основные шрифты
second_title: API обработки документов Aspose.Words
description: Узнайте, как уменьшить размер PDF-файла, не встраивая основные шрифты, с помощью Aspose.Words для .NET. Следуйте нашему пошаговому руководству по оптимизации PDF-файлов.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---
## Введение

Вы когда-нибудь ломали голову, задаваясь вопросом, почему ваши PDF-файлы такие большие? Ну, ты не одинок. Одной из распространенных проблем является встраивание основных шрифтов, таких как Arial и Times New Roman. К счастью, в Aspose.Words for .NET есть отличный способ решить эту проблему. В этом уроке я покажу вам, как уменьшить размер PDF-файла, избегая встраивания этих основных шрифтов. Давайте погрузимся прямо сейчас!

## Предварительные условия

Прежде чем мы отправимся в это увлекательное путешествие, давайте убедимся, что у вас есть все необходимое. Вот краткий контрольный список:

-  Aspose.Words для .NET: убедитесь, что у вас установлен Aspose.Words для .NET. Если у вас его еще нет, вы можете скачать его[здесь](https://releases.aspose.com/words/net/).
- Среда разработки: вам понадобится среда разработки, такая как Visual Studio.
- Документ Word: для этого урока мы будем использовать документ Word (например, «Rendering.docx»).
- Базовые знания C#. Базовое понимание C# поможет вам в дальнейшем.

Хорошо, теперь, когда у нас все готово, давайте перейдем к делу!

## Импортировать пространства имен

Прежде всего, давайте импортируем необходимые пространства имен. Этот шаг гарантирует, что у нас есть доступ ко всем необходимым функциям Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Шаг 1. Инициализируйте каталог документов

Прежде чем мы начнем манипулировать нашим документом, нам нужно указать каталог, в котором хранятся наши документы. Это необходимо для доступа к файлам.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем, где находится ваш документ Word.

## Шаг 2. Загрузите документ Word

Далее нам нужно загрузить документ Word, который мы хотим преобразовать в PDF. В этом примере мы используем документ с именем «Rendering.docx».

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Эта строка кода загружает документ в память, готовый к дальнейшей обработке.

## Шаг 3. Настройте параметры сохранения PDF-файла

Теперь наступает волшебная часть! Мы настроим параметры сохранения PDF, чтобы избежать внедрения основных шрифтов. Это ключевой шаг, который помогает уменьшить размер PDF-файла.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    UseCoreFonts = true
};
```

 Параметр`UseCoreFonts` к`true` гарантирует, что основные шрифты, такие как Arial и Times New Roman, не будут встроены в PDF-файл, что значительно уменьшает размер файла.

## Шаг 4. Сохраните документ в формате PDF.

Наконец, мы сохраняем документ Word в формате PDF, используя настроенные параметры сохранения. На этом этапе создается PDF-файл без внедрения основных шрифтов.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

И вот оно! Ваш PDF-файл теперь сохраняется в указанном каталоге без этих громоздких основных шрифтов.

## Заключение

Уменьшить размер PDF-файла можно с легкостью с помощью Aspose.Words для .NET. Избегая внедрения основных шрифтов, вы можете значительно уменьшить размер файла, упрощая совместное использование и хранение ваших документов. Я надеюсь, что этот урок был полезен и дал вам четкое представление о процессе. Помните: небольшие изменения могут иметь большое значение!

## Часто задаваемые вопросы

### Почему мне следует избегать встраивания основных шрифтов в PDF-файлы?
Отказ от внедрения основных шрифтов уменьшает размер файла, упрощая его совместное использование и хранение.

### Могу ли я по-прежнему правильно просматривать PDF-файл без встроенных основных шрифтов?
Да, основные шрифты, такие как Arial и Times New Roman, обычно доступны в большинстве систем.

### Что делать, если мне нужно встроить собственные шрифты?
 Вы можете настроить`PdfSaveOptions`для встраивания определенных шрифтов по мере необходимости.

### Можно ли использовать Aspose.Words для .NET бесплатно?
 Для Aspose.Words для .NET требуется лицензия. Вы можете получить бесплатную пробную версию[здесь](https://releases.aspose.com/).

### Где я могу найти дополнительную документацию по Aspose.Words для .NET?
 Вы можете найти подробную документацию[здесь](https://reference.aspose.com/words/net/).