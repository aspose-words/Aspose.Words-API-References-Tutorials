---
title: Формат 1Bpp Индексированный
linktitle: Формат 1Bpp Индексированный
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как форматировать изображения в формате 1 бит на пиксель, проиндексированные с помощью Aspose.Words для .NET. Полное руководство для изображений с низкой глубиной цвета.
type: docs
weight: 10
url: /ru/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
В этом руководстве мы рассмотрим исходный код C#, предоставленный для функции «Формат 1Bpp Indexed» с Aspose.Words для .NET. Эта функция позволяет форматировать изображения в документе в формате PNG с глубиной цвета 1 бит на пиксель (1 бит на пиксель) и индексированным цветовым режимом.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили среду разработки с Aspose.Words для .NET. Убедитесь, что вы добавили необходимые ссылки и импортировали соответствующие пространства имен.

## Шаг 2: Загрузка документа

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 На этом шаге мы загружаем документ с помощью`Document` Метод и передача пути к файлу DOCX для загрузки.

## Шаг 3. Настройте параметры резервного копирования образа

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 На этом этапе мы настраиваем параметры резервного копирования для образов. Мы создаем новый`ImageSaveOptions`объект, указывающий желаемый формат сохранения, здесь «Png» для формата PNG. Мы также определяем страницу для включения в изображение, черно-белый цветовой режим и индексированный формат пикселей 1 бит на пиксель.

## Шаг 4. Резервное копирование изображений

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 На этом последнем шаге мы сохраняем изображения документа в формате PNG, используя`Save` метод и передачу пути к выходному файлу вместе с указанными параметрами сохранения.

Теперь вы можете запустить исходный код для форматирования изображения документа в формате PNG с индексированной глубиной цвета 1 бит на пиксель. Полученный файл будет сохранен в указанном каталоге с именем «WorkingWithImageSaveOptions.Format1BppIndexed.Png».

### Пример исходного кода для формата 1Bpp, проиндексированного с использованием Aspose.Words для .NET

```csharp 
 
			 // Путь к вашему каталогу документов
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Заключение

В этом руководстве мы рассмотрели функцию индексированного формата 1Bpp с Aspose.Words для .NET. Мы научились форматировать изображения в документе в формате PNG с глубиной цвета 1 бит на пиксель (1 бит на пиксель) и индексированным цветовым режимом.

Эта функция полезна, когда вы хотите получить изображения с низкой глубиной цвета и небольшим размером файла. Индексированный формат 1Bpp позволяет представлять изображения с помощью индексированной цветовой палитры, что может быть полезно для некоторых конкретных приложений.

Aspose.Words для .NET предлагает широкий спектр расширенных функций для обработки и создания документов. Формат 1Bpp Indexed — один из многих мощных инструментов, которые он предоставляет в ваше распоряжение.