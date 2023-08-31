---
title: Привязать SDT к пользовательской части Xml
linktitle: Привязать SDT к пользовательской части Xml
second_title: API обработки документов Aspose.Words
description: Узнайте, как привязать SDT к пользовательской части Xml с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

В этом руководстве показано, как привязать тег структурированного документа (SDT) к пользовательской части Xml с помощью Aspose.Words для .NET. SDT позволяют добавлять структурированные элементы управления содержимым в документ Word, а CustomXmlParts предоставляет способ хранения пользовательских XML-данных, связанных с документом.

## Предпосылки
Чтобы следовать этому руководству, вам необходимо иметь следующее:

- Установлена библиотека Aspose.Words for .NET.
- Базовые знания C# и XML.

## Шаг 1. Настройте каталог документов
 Начните с настройки пути к каталогу документов. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу, в котором вы хотите сохранить документ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Создайте документ и CustomXmlPart
 Создайте новый экземпляр`Document` класс и`CustomXmlPart` для хранения пользовательских данных XML. Пользовательский XML должен быть в допустимом формате XML. В этом примере мы используем простую строку XML`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Шаг 3. Добавьте в документ тег StructuredDocumentTag (SDT)
 Добавить`StructuredDocumentTag` в документ, чтобы служить в качестве элемента управления содержимым. Укажите`SdtType` как`PlainText` и`MarkupLevel` как`Block` для создания SDT блочного уровня.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Шаг 4. Установите сопоставление XML для SDT
 Сопоставьте SDT с`CustomXmlPart` с помощью`SetMapping` метод`XmlMapping` свойство. Укажите`CustomXmlPart` , выражение XPath для поиска нужного узла XML и префикс пространства имен, если необходимо. В этом примере мы сопоставляем SDT с`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Шаг 5: Сохраните документ
 Сохраните измененный документ в указанную директорию с помощью`Save` метод. Укажите желаемое имя файла с соответствующим расширением файла. В этом примере мы сохраняем документ как «WorkingWithSdt.BindSDTtoCustomXmlPart.doc».

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Пример исходного кода для Bind Sd Tto Custom Xml Part с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Вот и все! Вы успешно привязали SDT к CustomXmlPart в документе Word, используя Aspose.Words для .NET.