---
title: Установить папку с изображениями
linktitle: Установить папку с изображениями
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить папку с изображениями при экспорте в Markdown с помощью Aspose.Words для .NET. Настройте размещение изображений для лучшей организации и интеграции.
type: docs
weight: 10
url: /ru/net/programming-with-markdownsaveoptions/set-images-folder/
---

Вот пошаговое руководство, объясняющее следующий исходный код C#, который помогает установить папку изображений для параметров экспорта Markdown с использованием библиотеки Aspose.Words для .NET. Перед использованием этого кода убедитесь, что вы включили библиотеку Aspose.Words в свой проект.

## Шаг 1. Установите путь к каталогу документов

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Обязательно укажите правильный путь к каталогу документов, где находится документ, содержащий изображения.

## Шаг 2: Загрузите документ, содержащий изображения

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Мы загружаем указанный документ, содержащий изображения, которые мы хотим экспортировать, с параметрами Markdown.

## Шаг 3: Установите папку изображений для параметров экспорта Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Мы создаем экземпляр`MarkdownSaveOptions` и укажите путь к папке с изображениями с помощью`ImagesFolder` свойство. Обязательно укажите правильный путь к папке, в которой вы хотите сохранить экспортированные изображения.

## Шаг 4. Сохраните документ с параметрами экспорта Markdown.

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Мы сохраняем документ в поток памяти, используя указанные параметры экспорта Markdown. Затем вы можете использовать поток для выполнения других операций, таких как сохранение содержимого Markdown в файл.

### Пример исходного кода для установки папки изображений для MarkdownSaveOptions с Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Этот исходный код демонстрирует, как загрузить документ, содержащий изображения, а затем установить папку изображений для параметров экспорта Markdown. Затем, используя указанные параметры, документ сохраняется в потоке памяти. Это позволяет настроить расположение папки с изображениями при экспорте содержимого Markdown.