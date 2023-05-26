---
title: PDF إلى Docx
linktitle: PDF إلى Docx
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستندات PDF إلى تنسيق Docx باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /tr/net/basic-conversions/pdf-to-docx/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند PDF إلى تنسيق Docx. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` كائن من خلال توفير المسار إلى مستند PDF الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Pdf Document.pdf");
```

## الخطوة 2: حفظ المستند بتنسيق Docx

 بعد ذلك ، احفظ المستند بتنسيق Docx عن طريق استدعاء ملف`Save` طريقة على`Document`كائن وتوفير المسار واسم الملف لمستند Docx الناتج:

```csharp
doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
```

هذا كل شيء! لقد نجحت في تحويل مستند PDF إلى تنسيق Docx باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Pdf To Docx باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Pdf Document.pdf");

	doc.Save(dataDir + "BaseConversions.PdfToDocx.docx");
	
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.