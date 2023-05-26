---
title: كشف توقيعات الوثيقة
linktitle: كشف توقيعات الوثيقة
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لاكتشاف التوقيعات الرقمية في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/programming-with-fileformat/detect-document-signatures/
---

تقدم هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة الكشف عن توقيع المستند مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية اكتشاف التوقيعات الرقمية في مستند.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: كشف التوقيعات الرقمية

 بعد ذلك ، نستخدم ملف`DetectFileFormat` طريقة`FileFormatUtil` فئة للكشف عن معلومات تنسيق الملف. في هذا المثال ، نفترض أن المستند يسمى "Digitallyigned.docx" وموجود في دليل المستندات المحدد.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## الخطوة 3: تحقق من وجود توقيعات رقمية

 نتحقق مما إذا كان المستند يحتوي على توقيعات رقمية باستخدام امتداد`HasDigitalSignature` ممتلكات`FileFormatInfo` هدف. إذا تم الكشف عن التوقيعات الرقمية ، فإننا نعرض رسالة تشير إلى أن التوقيعات ستفقد إذا تم فتح / حفظ المستند باستخدام Aspose.Words.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

هذا كل شئ ! لقد نجحت في اكتشاف توقيعات رقمية في مستند باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لاكتشاف توقيعات المستندات باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```
