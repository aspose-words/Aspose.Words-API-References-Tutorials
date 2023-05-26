---
title: ربط SDT بجزء Xml المخصص
linktitle: ربط SDT بجزء Xml المخصص
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية ربط SDT بجزء Xml مخصص باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

يوضح هذا البرنامج التعليمي كيفية ربط علامة المستند المهيكل (SDT) بجزء Xml مخصص باستخدام Aspose.Words for .NET. تسمح لك أدوات SDT بإضافة عناصر تحكم محتوى منظم إلى مستند Word ، وتوفر CustomXmlParts طريقة لتخزين بيانات XML المخصصة المرتبطة بالمستند.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # و XML.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستند الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند و CustomXmlPart
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`CustomXmlPart` لتخزين بيانات XML المخصصة. يجب أن يكون XML المخصص بتنسيق XML صالح. في هذا المثال ، نستخدم سلسلة XML بسيطة`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## الخطوة 3: إضافة StructuredDocumentTag (SDT) إلى المستند
 أضف`StructuredDocumentTag`إلى المستند ليكون بمثابة عنصر تحكم المحتوى. حدد ال`SdtType` مثل`PlainText` و ال`MarkupLevel` مثل`Block` لإنشاء المعاملة الخاصة والتفضيلية على مستوى الكتلة.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## الخطوة 4: تعيين تعيين XML لـ SDT
 قم بتعيين SDT إلى ملف`CustomXmlPart` باستخدام ملف`SetMapping` طريقة`XmlMapping` ملكية. حدد ال`CustomXmlPart` ، وتعبير XPath لتحديد موقع عقدة XML المطلوبة ، وبادئة مساحة الاسم إذا لزم الأمر. في هذا المثال ، نقوم بتعيين المعاملة الخاصة والتفضيلية إلى`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## الخطوة 5: احفظ المستند
 احفظ المستند المعدل إلى الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### مثال على شفرة المصدر لجزء Bind Sd Tto Custom Xml باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

هذا كل شيء! لقد نجحت في ربط SDT بـ CustomXmlPart في مستند Word باستخدام Aspose.Words for .NET.