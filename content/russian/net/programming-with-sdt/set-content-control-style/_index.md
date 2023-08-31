---
title: Установить стиль управления контентом
linktitle: Установить стиль управления контентом
second_title: API обработки документов Aspose.Words
description: Узнайте, как установить стиль элемента управления содержимым в документе Word с помощью Aspose.Words для .NET, применяя согласованное форматирование.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/set-content-control-style/
---

В этом руководстве объясняется, как установить стиль элемента управления содержимым в документе Word с помощью Aspose.Words для .NET. Вы можете применять предопределенные или пользовательские стили к элементам управления содержимым для единообразного форматирования.

## Предварительные условия
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words для .NET.
- Базовые знания C# и обработки документов Word.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу ваших документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором находится ваш документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите документ и получите элемент управления содержимым
 Загрузите документ Word, используя`Document` конструктор, передавая путь к документу в качестве параметра. Получите желаемый элемент управления содержимым из документа. В этом примере мы предполагаем, что элемент управления содержимым — это первый структурированный тег документа в документе.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Шаг 3. Получите стиль и примените его к элементу управления содержимым.
 Получите нужный стиль из коллекции стилей документа. В этом примере мы получаем стиль «Цитата», используя`StyleIdentifier.Quote` . Затем присвойте полученный стиль`Style` свойство тега структурированного документа.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Шаг 4. Сохраните документ
 Сохраните измененный документ в указанную директорию, используя команду`Save` метод. Укажите желаемое имя файла с соответствующим расширением. В этом примере мы сохраняем документ как «WorkingWithSdt.SetContentControlStyle.docx».

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Пример исходного кода для установки стиля управления контентом с использованием Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Вот и все! Вы успешно установили стиль элемента управления содержимым в документе Word с помощью Aspose.Words для .NET.