---
title: إنشاء قسم تكرار الجدول المعين لجزء Xml المخصص
linktitle: إنشاء قسم تكرار الجدول المعين لجزء Xml المخصص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء جدول يحتوي على قسم متكرر معين إلى CustomXmlPart في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

يوضح هذا البرنامج التعليمي كيفية إنشاء جدول يحتوي على قسم متكرر معين لجزء Xml مخصص في مستند Word باستخدام Aspose.Words لـ .NET. يسمح لك قسم التكرار بإضافة صفوف ديناميكيًا استنادًا إلى بيانات XML المخزنة في جزء Xml المخصص.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند و DocumentBuilder
 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` لبناء محتوى الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إضافة بيانات XML مخصصة إلى CustomXmlPart
 إنشاء`CustomXmlPart` وإضافة بيانات XML مخصصة إليها. في هذا المثال، قمنا بإنشاء سلسلة XML تمثل مجموعة من الكتب مع عناوينها ومؤلفيها.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## الخطوة 4: إنشاء جدول وهيكل الجدول
 ابدأ في إنشاء جدول باستخدام`StartTable` طريقة`DocumentBuilder` . إضافة خلايا الجدول والمحتوى باستخدام`InsertCell`و`Write` طُرق.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## الخطوة 5: إنشاء قسم التكرار المعين لـ XML المخصص
 إنشاء`StructuredDocumentTag` مع`SdtType.RepeatingSection` لتمثيل القسم المتكرر. قم بتعيين تعيين XML للقسم المتكرر باستخدام`SetMapping` طريقة`XmlMapping` ملكية. في هذا المثال، نقوم بتعيين القسم المكرر إلى`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## الخطوة 6: إنشاء عنصر القسم المكرر وإضافة خلايا
 إنشاء`StructuredDocumentTag` مع`SdtType.RepeatingSectionItem` لتمثيل عنصر القسم المتكرر. قم بإلحاقه كطفل إلى قسم التكرار.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 إنشاء`Row` لتمثيل كل عنصر في القسم المكرر وإلحاقه بعنصر القسم المكرر.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## الخطوة 7: إضافة عناصر التحكم في المحتوى داخل قسم التكرار
 يخلق`StructuredDocumentTag` الكائنات مع`SdtType.PlainText`

  لتمثيل عناصر التحكم في محتوى العنوان والمؤلف. قم بتعيين تعيين XML لكل عنصر تحكم محتوى باستخدام`SetMapping` طريقة`XmlMapping` ملكية. في هذا المثال، نقوم بتعيين عنصر تحكم العنوان إلى`/books[1]/book[1]/title[1]` وسيطرة المؤلف على`/books[1]/book[1]/author[1]`.

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
 احفظ المستند المعدل في الدليل المحدد باستخدام الملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### مثال على التعليمات البرمجية المصدر لإنشاء قسم مكرر للجدول المعين لجزء Xml مخصص باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
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

هذا كل شيء! لقد نجحت في إنشاء جدول يحتوي على قسم متكرر تم تعيينه إلى CustomXmlPart في مستند Word الخاص بك باستخدام Aspose.Words for .NET.