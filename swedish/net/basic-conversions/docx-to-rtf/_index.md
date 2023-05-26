---
title: Docx إلى Rtf
linktitle: Docx إلى Rtf
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستندات Word من تنسيق Docx إلى تنسيق RTF باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-rtf/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق Docx إلى RTF. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: قراءة المستند من الدفق

أولاً ، افتح دفقًا لقراءة مستند Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## الخطوة الثانية: تحميل المستند

بعد ذلك ، قم بتحميل المستند من الدفق:

```csharp
Document doc = new Document(stream);
```

## الخطوة 3: إغلاق الدفق

نظرًا لأنه تم تحميل المستند في الذاكرة ، يمكنك إغلاق الدفق:

```csharp
stream.Close();
```

## الخطوة 4: إجراء العمليات على المستند

في هذه المرحلة ، يمكنك إجراء أي عمليات مطلوبة على المستند.

## الخطوة 5: حفظ المستند بتنسيق RTF

لحفظ المستند بتنسيق RTF ، احفظه في تدفق ذاكرة:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## الخطوة 6: إرجاع الدفق

قبل كتابة تدفق الذاكرة إلى ملف ، قم بإرجاع موضعه إلى الصفر:

```csharp
dstStream.Position = 0;
```

## الخطوة 7: كتابة الدفق إلى ملف

أخيرًا ، اكتب تدفق الذاكرة إلى ملف RTF:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق Docx إلى RTF باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Docx To Rtf باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// الوصول للقراءة فقط كافٍ لـ Aspose.Words لتحميل مستند.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	//يمكنك إغلاق الدفق الآن ، لم تعد هناك حاجة إليه لأن المستند موجود في الذاكرة.
	stream.Close();

	// ... افعل شيئًا ما مع المستند.

	// قم بتحويل المستند إلى تنسيق مختلف وحفظه في الدفق.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// قم بإرجاع موضع الدفق إلى الصفر بحيث يكون جاهزًا للقارئ التالي.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.