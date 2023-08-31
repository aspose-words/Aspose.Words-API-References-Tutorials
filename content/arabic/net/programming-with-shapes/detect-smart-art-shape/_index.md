---
title: كشف الشكل الفني الذكي
linktitle: كشف الشكل الفني الذكي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية اكتشاف أشكال Smart Art في مستند Word باستخدام Aspose.Words لـ .NET، وتحديد التمثيلات الرسومية.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/detect-smart-art-shape/
---

يشرح هذا البرنامج التعليمي كيفية اكتشاف أشكال Smart Art في مستند Word باستخدام Aspose.Words لـ .NET. الأشكال الفنية الذكية هي تمثيلات رسومية تستخدم لتقديم المعلومات والأفكار بشكل مرئي.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي يوجد به المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند
 قم بتحميل مستند Word باستخدام`Document` منشئ، وتمرير المسار إلى الوثيقة كمعلمة.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## الخطوة 3: اكتشاف الأشكال الفنية الذكية
 التكرار من خلال العقد الفرعية من النوع`Shape` في المستند باستخدام`GetChildNodes`طريقة. تحقق مما إذا كان كل شكل يحتوي على Smart Art باستخدام`HasSmart Art` ملكية.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## الخطوة 4: إخراج النتيجة
اطبع عدد الأشكال باستخدام Smart Art المكتشف في المستند.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### مثال على التعليمات البرمجية المصدر لـ Detect Smart Art Shape باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

هذا كل شيء! لقد نجحت في اكتشاف أشكال Smart Art في مستند Word الخاص بك باستخدام Aspose.Words for .NET.