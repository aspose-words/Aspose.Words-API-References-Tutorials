---
title: ربط SDT بجزء Xml المخصص
linktitle: ربط SDT بجزء Xml المخصص
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ربط SDT بجزء Xml مخصص باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

يوضح هذا البرنامج التعليمي كيفية ربط علامة الوثيقة المنظمة (SDT) بجزء Xml مخصص باستخدام Aspose.Words لـ .NET. تسمح لك SDTs بإضافة عناصر تحكم المحتوى المنظم إلى مستند Word، وتوفر CustomXmlParts طريقة لتخزين بيانات XML المخصصة المرتبطة بالمستند.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# وXML.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وCustomXmlPart
 إنشاء مثيل جديد لـ`Document` فئة و أ`CustomXmlPart` لتخزين بيانات XML المخصصة. يجب أن يكون XML المخصص بتنسيق XML صالحًا. في هذا المثال، نستخدم سلسلة XML بسيطة`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## الخطوة 3: إضافة StructuredDocumentTag (SDT) إلى المستند
 أضف`StructuredDocumentTag`إلى المستند ليكون بمثابة عنصر تحكم المحتوى. حدد ال`SdtType` مثل`PlainText` و ال`MarkupLevel` مثل`Block` لإنشاء SDT على مستوى الكتلة.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## الخطوة 4: قم بتعيين تعيين XML لـ SDT
 قم بتعيين المعاملة الخاصة والتفضيلية (SDT) إلى`CustomXmlPart` باستخدام`SetMapping` طريقة`XmlMapping` ملكية. حدد ال`CustomXmlPart` وتعبير XPath لتحديد موقع عقدة XML المطلوبة وبادئة مساحة الاسم إذا لزم الأمر. في هذا المثال، نقوم بتعيين المعاملة الخاصة والتفضيلية ل`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## الخطوة 5: احفظ المستند
 احفظ المستند المعدل في الدليل المحدد باستخدام الملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### مثال على التعليمات البرمجية المصدر لجزء Bind Sd Tto Custom Xml باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

هذا كل شيء! لقد نجحت في ربط SDT بـ CustomXmlPart في مستند Word الخاص بك باستخدام Aspose.Words for .NET.