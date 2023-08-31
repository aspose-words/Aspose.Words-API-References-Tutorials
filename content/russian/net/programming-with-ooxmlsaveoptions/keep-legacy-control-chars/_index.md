---
title: Сохранить устаревшие контрольные символы
linktitle: Сохранить устаревшие контрольные символы
second_title: API обработки документов Aspose.Words
description: Узнайте, как сохранить устаревшие управляющие символы при сохранении документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

В этом руководстве мы рассмотрим предоставленный исходный код C#, чтобы сохранить устаревшие управляющие символы при сохранении документа с использованием Aspose.Words для .NET. Эта функция позволяет сохранять специальные управляющие символы при преобразовании или сохранении документа.

## Шаг 1. Настройка среды

Прежде чем начать, убедитесь, что вы настроили среду разработки с Aspose.Words для .NET. Убедитесь, что вы добавили необходимые ссылки и импортировали соответствующие пространства имен.

## Шаг 2: Загрузка документа

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

 На этом шаге мы загружаем документ с помощью`Document` метода и передачи пути к файлу, содержащему унаследованные управляющие символы.

## Шаг 3. Настройка параметров резервного копирования OOXML

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

На этом шаге мы настроим параметры сохранения OOXML, создав новый`OoxmlSaveOptions`объект. Указываем желаемый формат сохранения (здесь,`FlatOpc` ) и включите`KeepLegacyControlChars` возможность сохранить устаревшие управляющие символы.

## Шаг 4. Сохранение документа с устаревшими управляющими символами

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

 На этом последнем шаге мы сохраняем документ, используя`Save` метод и передача пути к выходному файлу с`.docx` расширение вместе с указанными параметрами сохранения.

Теперь вы можете запустить исходный код, чтобы сохранить устаревшие управляющие символы при сохранении документа. Полученный файл будет сохранен в указанном каталоге с именем «WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx».

### Пример исходного кода для сохранения устаревших контрольных символов с использованием Aspose.Words для .NET 
```csharp

//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Заключение

В этом руководстве мы рассмотрели функциональность сохранения устаревших управляющих символов при сохранении документа с помощью Aspose.Words для .NET. Мы узнали, как сохранить те специальные символы, которые могут быть важны для правильного форматирования или отображения документа.

 Сохранение устаревших управляющих символов особенно полезно, когда Word обрабатывает документы, в которых используются старые или специальные функции, такие как специальные управляющие символы. Включив`KeepLegacyControlChars`вариант при сохранении документа, вы гарантируете, что эти символы сохранены.

Aspose.Words для .NET предлагает ряд гибких и мощных опций резервного копирования для удовлетворения ваших потребностей в работе с документами. Используя соответствующие параметры, вы можете настроить процесс резервного копирования, чтобы сохранить определенные характеристики ваших документов.

Не стесняйтесь включать эту функцию в свои проекты Aspose.Words для .NET, чтобы обеспечить целостность и сохранение устаревших управляющих символов в ваших документах.