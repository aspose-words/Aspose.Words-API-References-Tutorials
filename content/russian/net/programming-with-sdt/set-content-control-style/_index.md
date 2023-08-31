---
title: Установить стиль управления содержимым
linktitle: Установить стиль управления содержимым
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить стиль элемента управления содержимым в документе Word с помощью Aspose.Words для .NET, применяя единообразное форматирование.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/set-content-control-style/
---

В этом руководстве объясняется, как установить стиль элемента управления содержимым в документе Word с помощью Aspose.Words для .NET. К элементам управления содержимым можно применять предварительно определенные или настраиваемые стили для единообразного форматирования.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и Word Processing с документами Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите элемент управления содержимым
 Загрузите документ Word с помощью`Document` конструктор, передавая путь к документу в качестве параметра. Получите нужный элемент управления содержимым из документа. В этом примере мы предполагаем, что элемент управления содержимым является первым тегом структурированного документа в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Получите стиль и примените его к элементу управления содержимым
 Получите нужный стиль из коллекции стилей документа. В этом примере мы извлекаем стиль «Цитата» с помощью`StyleIdentifier.Quote` . Затем назначьте полученный стиль`Style` свойство тега структурированного документа.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Шаг 4: Сохраните документ
 Сохраните измененный документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.SetContentControlStyle.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Пример исходного кода для установки стиля управления содержимым с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Вот и все! Вы успешно установили стиль элемента управления содержимым в документе Word с помощью Aspose.Words для .NET.