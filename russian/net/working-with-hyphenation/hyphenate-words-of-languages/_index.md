---
title: Перенос слов языков
linktitle: Перенос слов языков
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как расставлять переносы слов на разных языках в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-hyphenation/hyphenate-words-of-languages/
---

В этом пошаговом руководстве мы расскажем вам, как расставлять переносы слов на разных языках в документах Word с помощью Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы еще этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объекта документа

 Сначала инициализируйте`Document` объект, указав путь к исходному документу, содержащему текст на разных языках:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "German text.docx");
```

## Шаг 2: Сохранение словарей переносов

Затем сохраните словари переносов для разных языков, которые вы хотите обработать. В этом примере мы регистрируем словари для американского английского и швейцарского немецкого:

```csharp
Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");
```

Убедитесь, что в вашем каталоге данных есть соответствующие файлы словарей.

## Шаг 3: Обработка слов по переносу

 Теперь вы можете использовать функции расстановки переносов для обработки слов на разных языках. Вы можете использовать различные способы`Document` или`DocumentBuilder`в зависимости от ваших конкретных потребностей.

```csharp
// Пример: использование метода Hyphenate DocumentBuilder
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Example of text to hyphenate");
builder.InsertHyphenation();
```

## Шаг 4: Сохраните документ

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "TreatmentByCesure.pdf");
```

Так ! Вы успешно обработали слова, расставив их через дефис на разных языках в документе Word, используя Aspose.Words для .NET.

### Пример исходного кода для расстановки переносов слов с использованием Aspose.Words для .NET

	```csharp
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "German text.docx");

	Hyphenation.RegisterDictionary("en-US", dataDir + "hyph_en_US.dic");
	Hyphenation.RegisterDictionary("de-CH", dataDir + "hyph_de_CH.dic");

	doc.Save(dataDir + "TreatmentByCesure.pdf");
	```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими потребностями.
