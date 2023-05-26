---
title: Docx إلى Pdf
linktitle: Docx إلى Pdf
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستندات Word من Docx إلى PDF باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-pdf/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق Docx إلى PDF. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` كائن مع المسار إلى مستندك المصدر بتنسيق Docx:

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 2: حفظ المستند بتنسيق PDF

 بعد ذلك ، احفظ المستند بتنسيق PDF عن طريق استدعاء ملف`Save` طريقة على`Document` كائن وتوفير المسار واسم الملف لمستند PDF الناتج:

```csharp
doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
```

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق Docx إلى PDF باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Docx To Pdf باستخدام Aspose.Words for .NET

```csharp

	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(MyDir + "BaseConversions.DocxToPdf.pdf");
	
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.
