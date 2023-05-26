---
title: Docx إلى Txt
linktitle: Docx إلى Txt
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستندات Word من Docx إلى نص عادي (Txt) باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /sv/net/basic-conversions/docx-to-txt/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق Docx إلى نص عادي (Txt). سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` كائن مع المسار إلى مستندك المصدر بتنسيق Docx:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## الخطوة 2: حفظ المستند بتنسيق Txt

 بعد ذلك ، احفظ المستند بتنسيق نص عادي (Txt) عن طريق استدعاء ملف`Save` طريقة على`Document` كائن وتوفير المسار واسم الملف لمستند Txt الناتج:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");
```

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق Docx إلى نص عادي (Txt) باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Docx To Txt باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToTxt.txt");

```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.