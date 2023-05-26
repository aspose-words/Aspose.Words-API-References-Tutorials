---
title: إنشاء مقطع مكرر للجدول معين إلى جزء Xml مخصص
linktitle: إنشاء مقطع مكرر للجدول معين إلى جزء Xml مخصص
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء جدول مع قسم مكرر معين إلى CustomXmlPart في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

يوضح هذا البرنامج التعليمي كيفية إنشاء جدول مع قسم مكرر معين إلى جزء Xml مخصص في مستند Word باستخدام Aspose.Words for .NET. يسمح لك قسم التكرار بإضافة صفوف ديناميكيًا استنادًا إلى بيانات XML المخزنة في جزء Xml المخصص.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستند الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند و DocumentBuilder
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` لبناء محتوى المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة بيانات XML مخصصة إلى CustomXmlPart
 إنشاء`CustomXmlPart` وإضافة بيانات XML المخصصة إليها. في هذا المثال ، نقوم بإنشاء سلسلة XML تمثل مجموعة من الكتب بعناوينها ومؤلفيها.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## الخطوة 4: إنشاء هيكل جدول وجدول
 ابدأ في إنشاء جدول باستخدام ملف`StartTable` طريقة`DocumentBuilder` . أضف خلايا الجدول والمحتوى باستخدام ملف`InsertCell` و`Write` طُرق.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## الخطوة 5: إنشاء قسم التكرار المعين إلى XML المخصص
 إنشاء`StructuredDocumentTag` مع`SdtType.RepeatingSection` لتمثيل قسم التكرار. قم بتعيين مخطط XML للقسم المكرر باستخدام امتداد`SetMapping` طريقة`XmlMapping` ملكية. في هذا المثال ، نقوم بتعيين قسم التكرار إلى`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## الخطوة 6: إنشاء عنصر قسم مكرر وإضافة خلايا
 إنشاء`StructuredDocumentTag` مع`SdtType.RepeatingSectionItem` لتمثيل عنصر القسم المكرر. قم بإلحاقه كطفل بقسم التكرار.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 إنشاء`Row`لتمثيل كل عنصر في قسم التكرار وإلحاقه بعنصر القسم المكرر.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## الخطوة 7: إضافة عناصر تحكم المحتوى داخل قسم التكرار
 يخلق`StructuredDocumentTag` الأشياء ذات`SdtType.PlainText`

  لتمثيل العنوان وعناصر تحكم محتوى المؤلف. قم بتعيين مخطط XML لكل عنصر تحكم محتوى باستخدام ملف`SetMapping` طريقة`XmlMapping` ملكية. في هذا المثال ، نقوم بتعيين عنصر تحكم العنوان إلى`/books[1]/book[1]/title[1]` وسيطر المؤلف على`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## الخطوة 8: احفظ المستند
 احفظ المستند المعدل إلى الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### مثال على شفرة المصدر لإنشاء قسم مكرر للجدول معين إلى جزء Xml مخصص باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

هذا كل شيء! لقد نجحت في إنشاء جدول به قسم مكرر تم تعيينه إلى CustomXmlPart في مستند Word باستخدام Aspose.Words for .NET.