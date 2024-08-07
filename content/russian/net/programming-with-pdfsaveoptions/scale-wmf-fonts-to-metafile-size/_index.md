---
title: Уменьшите размер PDF с помощью масштабирования шрифтов Wmf до размера метафайла
linktitle: Уменьшите размер PDF с помощью масштабирования шрифтов Wmf до размера метафайла
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по уменьшению размера PDF с помощью масштабирования шрифтов WMF до размера метафайла при преобразовании в PDF с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---
## Введение

При работе с PDF-файлами, особенно с файлами, созданными из документов Word, содержащих графику WMF (метафайл Windows), управление размером может стать решающим аспектом обработки документов. Один из способов контролировать размер PDF-файла — настроить способ отображения шрифтов WMF в документе. В этом уроке мы рассмотрим, как уменьшить размер PDF-файла путем масштабирования шрифтов WMF до размера метафайла с помощью Aspose.Words для .NET.

## Предварительные условия

Прежде чем приступить к выполнению шагов, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET: убедитесь, что у вас установлена библиотека Aspose.Words. Если нет, вы можете[скачай это здесь](https://releases.aspose.com/words/net/).
2. Среда разработки. В этом руководстве предполагается, что у вас настроена среда разработки .NET (например, Visual Studio), в которой вы можете писать и выполнять код C#.
3. Базовые знания программирования .NET. Знание основных концепций программирования .NET и синтаксиса C# будет полезным.
4. Документ Word с графикой WMF. Вам понадобится документ Word, содержащий графику WMF. Вы можете использовать свой собственный документ или создать его для тестирования.

## Импортировать пространства имен

Сначала вам необходимо импортировать необходимые пространства имен в ваш проект C#. Это даст вам доступ к классам и методам, необходимым для работы с Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Шаг 1. Загрузите документ Word

 Для начала загрузите документ Word, содержащий графику WMF. Это делается с помощью`Document` класс из Aspose.Words.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Загрузите документ
Document doc = new Document(dataDir + "WMF with text.docx");
```

 Здесь,`dataDir` является заполнителем для пути к каталогу вашего документа. Мы создаем экземпляр`Document` класс, передав путь к файлу Word. При этом документ загружается в память, готовый к дальнейшей обработке.

## Шаг 2. Настройте параметры рендеринга метафайла

 Далее вам необходимо настроить параметры рендеринга метафайла. В частности, установите`ScaleWmfFontsToMetafileSize`собственность`false`. Это определяет, масштабируются ли шрифты WMF в соответствии с размером метафайла.

```csharp
// Создайте новый экземпляр MetafileRenderingOptions.
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
    ScaleWmfFontsToMetafileSize = false
};
```

`MetafileRenderingOptions` Класс предоставляет параметры отображения метафайлов (например, WMF). Установив`ScaleWmfFontsToMetafileSize` к`false`, вы указываете Aspose.Words не масштабировать шрифты в соответствии с размером метафайла, что может помочь уменьшить общий размер PDF-файла.

## Шаг 3. Установите параметры сохранения PDF-файла.

Теперь настройте параметры сохранения PDF, чтобы использовать только что установленные параметры рендеринга метафайла. Это сообщает Aspose.Words, как обрабатывать метафайлы при сохранении документа в формате PDF.

```csharp
// Создайте новый экземпляр PdfSaveOptions.
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    MetafileRenderingOptions = metafileRenderingOptions
};
```

`PdfSaveOptions` Класс позволяет указать различные настройки для сохранения документа в формате PDF. Назначив ранее настроенный`MetafileRenderingOptions` к`MetafileRenderingOptions` собственность`PdfSaveOptions`, вы гарантируете, что документ сохранен в соответствии с желаемыми настройками рендеринга метафайла.

## Шаг 4. Сохраните документ в формате PDF.

Наконец, сохраните документ Word в формате PDF, используя настроенные параметры сохранения. При этом к выходному PDF-файлу будут применены все настройки, включая параметры рендеринга метафайла.


```csharp
// Сохраните документ в формате PDF
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

 На этом этапе`Save` метод`Document` Класс используется для экспорта документа в файл PDF. Указывается путь, по которому будет сохранен PDF-файл, а также`PdfSaveOptions` которые включают настройки рендеринга метафайлов.

## Заключение

Масштабируя шрифты WMF до размера метафайла, вы можете значительно уменьшить размер PDF-файлов, созданных из документов Word. Этот метод помогает оптимизировать хранение и распространение документов без ущерба для качества визуального контента. Выполнение описанных выше шагов гарантирует, что ваши PDF-файлы будут более управляемыми и эффективными по размеру.

## Часто задаваемые вопросы

### Что такое WMF и почему это важно для размера PDF?

WMF (метафайл Windows) — это графический формат, используемый в Microsoft Windows. Он может содержать как векторные, так и растровые данные. Поскольку векторные данные можно масштабировать и манипулировать ими, важно правильно обращаться с ними, чтобы избежать создания неоправданно больших файлов PDF.

### Как масштабирование шрифтов WMF до размера метафайла влияет на PDF-файл?

Масштабирование шрифтов WMF до размера метафайла может помочь уменьшить общий размер PDF-файла, избегая рендеринга шрифтов с высоким разрешением, который может увеличить размер файла.

### Могу ли я использовать другие форматы метафайлов с Aspose.Words?

Да, Aspose.Words поддерживает различные форматы метафайлов, включая EMF (расширенный метафайл) в дополнение к WMF.

### Применим ли этот метод ко всем типам документов Word?

Да, этот метод можно применить к любому документу Word, содержащему графику WMF, что помогает оптимизировать размер создаваемого PDF-файла.

### Где я могу найти дополнительную информацию об Aspose.Words?

 Вы можете узнать больше об Aspose.Words в[Документация Aspose.Words](https://reference.aspose.com/words/net/) . Для загрузки, пробных версий и поддержки посетите[Страница загрузки Aspose.Words](https://releases.aspose.com/words/net/), [Купить Aspose.Words](https://purchase.aspose.com/buy), [Бесплатная пробная версия](https://releases.aspose.com/), [Временная лицензия](https://purchase.aspose.com/temporary-license/) , и[Поддерживать](https://forum.aspose.com/c/words/8).