---
title: نطاق علامات المستند المنظم ابدأ تعيين XML
linktitle: نطاق علامات المستند المنظم ابدأ تعيين XML
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إعداد تعيين XML لنطاق علامات مستند منظم يبدأ في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

يشرح هذا البرنامج التعليمي كيفية إعداد تعيين XML لنطاق علامات مستند منظم يبدأ في مستند Word باستخدام Aspose.Words for .NET. يسمح لك تعيين XML بعرض أجزاء محددة من مصدر بيانات XML ضمن عنصر تحكم المحتوى.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وإنشاء جزء XML
 قم بتحميل مستند Word باستخدام`Document` منشئ، وتمرير المسار إلى الوثيقة كمعلمة. قم بإنشاء جزء XML يحتوي على البيانات التي تريد عرضها ضمن علامة المستند المنظمة.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## الخطوة 3: تعيين تعيين XML لعلامة المستند المنظمة
استرداد نطاق علامات المستند المنظم بدءًا من المستند. بعد ذلك، قم بتعيين تعيين XML لعلامة المستند المنظمة لعرض جزء معين من جزء XML المخصص باستخدام تعبير XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل في الدليل المحدد باستخدام الملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### مثال للتعليمة البرمجية المصدر لنطاق علامات المستند الهيكلي، ابدأ تعيين Xml باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// قم بإنشاء جزء XML يحتوي على بيانات وأضفه إلى مجموعة CustomXmlPart الخاصة بالمستند.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// قم بإنشاء StructuredDocumentTag الذي سيعرض محتويات CustomXmlPart في المستند.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// إذا قمنا بتعيين تعيين لـ StructuredDocumentTag الخاص بنا،
	// سيعرض فقط جزءًا من CustomXmlPart الذي يشير إليه XPath.
	// سيشير XPath هذا إلى محتويات العنصر "<text>" الثاني للعنصر "<root>" الأول في CustomXmlPart الخاص بنا.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

هذا كل شيء! لقد قمت بنجاح بإعداد تعيين XML لنطاق علامات مستند منظم يبدأ في مستند Word الخاص بك باستخدام Aspose.Words for .NET.