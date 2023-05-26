---
title: Загрузить словарь переносов для языка
linktitle: Загрузить словарь переносов для языка
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как загрузить словарь переносов для определенного языка в Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-hyphenation/load-hyphenation-dictionary-for-language/
---

В этом пошаговом руководстве мы покажем вам, как загрузить словарь переносов для определенного языка в Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы еще этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Загрузка документа

Сначала загрузите документ из указанного каталога:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Шаг 2: Загрузка словаря переносов

Затем откройте поток в файл словаря переносов и сохраните его для нужного языка. В этом примере мы загружаем словарь для швейцарского немецкого языка (de-CH):

```csharp
Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);
```

Убедитесь, что у вас есть соответствующий файл словаря в вашем каталоге данных.

## Шаг 3: Сохраните измененный документ

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Так ! Вы успешно загрузили словарь переносов для определенного языка в Aspose.Words для .NET.

### Пример исходного кода для загрузки словаря переносов для языка с использованием Aspose.Words для .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");

Stream stream = File.OpenRead(dataDir + "hyph_de_CH.dic");
Hyphenation.RegisterDictionary("de-CH", stream);

doc.Save(dataDir + "ProcessingByBreakingWithDictionary.pdf");
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими потребностями.