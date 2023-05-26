---
title: نطاق علامة المستند المهيكلة بدء تعيين Xml
linktitle: نطاق علامة المستند المهيكلة بدء تعيين Xml
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إعداد تعيين XML لنطاق علامة مستند منظم يبدأ في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

يشرح هذا البرنامج التعليمي كيفية إعداد تعيين XML لنطاق علامة مستند منظم يبدأ في مستند Word باستخدام Aspose.Words for .NET. يتيح لك تعيين XML عرض أجزاء معينة من مصدر بيانات XML داخل عنصر تحكم المحتوى.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند وإنشاء جزء XML
 قم بتحميل مستند Word باستخدام ملف`Document` مُنشئ ، تمرير المسار إلى المستند كمعامل. قم بإنشاء جزء XML يحتوي على البيانات التي تريد عرضها داخل علامة المستند المهيكلة.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## الخطوة 3: تعيين مخطط XML لعلامة المستند المهيكلة
استرجع نطاق علامة المستند المنظم بدءًا من المستند. بعد ذلك ، قم بتعيين مخطط XML لعلامة المستند المركب لعرض جزء معين من جزء XML المخصص باستخدام تعبير XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## الخطوة 4: احفظ المستند
 احفظ المستند المعدل إلى الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### مثال على شفرة المصدر لنطاق علامة المستند المهيكل ابدأ تعيين Xml باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// أنشئ جزء XML يحتوي على بيانات وأضفه إلى مجموعة CustomXmlPart الخاصة بالمستند.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// قم بإنشاء StructuredDocumentTag الذي سيعرض محتويات CustomXmlPart الخاصة بنا في المستند.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// إذا قمنا بتعيين خريطة لعلامة StructuredDocumentTag الخاصة بنا ،
	// سيعرض فقط جزءًا من CustomXmlPart الذي يشير إليه XPath.
	// سيشير XPath هذا إلى المحتوى الثاني "<text>" للعنصر الأول "<root>" في CustomXmlPart الخاص بنا.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

هذا كل شيء! لقد نجحت في إعداد تعيين XML لنطاق علامة مستند منظم يبدأ في مستند Word باستخدام Aspose.Words for .NET.