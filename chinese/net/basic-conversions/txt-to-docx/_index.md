---
title: TXT إلى Docx
linktitle: TXT إلى Docx
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل ملفات النص العادي (Txt) إلى مستندات Word (Docx) باستخدام Aspose.Words for .NET. البرنامج التعليمي خطوة بخطوة مع رمز المثال.
type: docs
weight: 10
url: /zh/net/basic-conversions/txt-to-docx/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل ملف نصي عادي (Txt) إلى مستند Word بتنسيق Docx. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` كائن من خلال توفير المسار إلى ملف النص العادي الخاص بك:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "English text.txt");
```

## الخطوة 2: حفظ المستند بتنسيق Docx

 بعد ذلك ، احفظ المستند بتنسيق Docx عن طريق استدعاء ملف`Save` طريقة على`Document`كائن وتوفير المسار واسم الملف لمستند Docx الناتج:

```csharp
doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");
```

هذا كل شيء! لقد نجحت في تحويل ملف نص عادي (Txt) إلى مستند Word بتنسيق Docx باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Txt To Docx باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// يتم الكشف عن ترميز الملف النصي تلقائيًا.
	Document doc = new Document(MyDir + "English text.txt");

	doc.Save(dataDir + "BaseConversions.TxtToDocx.docx");

```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.