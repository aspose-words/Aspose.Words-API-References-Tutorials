---
title: كشف شكل الفن الذكي
linktitle: كشف شكل الفن الذكي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية اكتشاف أشكال الفن الذكي في مستند Word باستخدام Aspose.Words for .NET ، مع تحديد التمثيلات الرسومية.
type: docs
weight: 10
url: /it/net/programming-with-shapes/detect-smart-art-shape/
---

يشرح هذا البرنامج التعليمي كيفية اكتشاف أشكال Smart Art في مستند Word باستخدام Aspose.Words for .NET. أشكال الفن الذكي هي تمثيلات رسومية تُستخدم لتقديم المعلومات والأفكار بشكل مرئي.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند
 قم بتحميل مستند Word باستخدام ملف`Document` مُنشئ ، تمرير المسار إلى المستند كمعامل.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## الخطوة الثالثة: اكتشاف الأشكال الفنية الذكية
كرر من خلال العقد الفرعية من النوع`Shape` في المستند باستخدام امتداد`GetChildNodes` طريقة. تحقق مما إذا كان كل شكل يحتوي على Smart Art باستخدام ملف`HasSmart Art` ملكية.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## الخطوة 4: إخراج النتيجة
اطبع عدد الأشكال باستخدام Smart Art المكتشف في المستند.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### مثال على شفرة المصدر لـ Detect Smart Art Shape باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

هذا كل شيء! لقد نجحت في اكتشاف أشكال Smart Art في مستند Word باستخدام Aspose.Words for .NET.