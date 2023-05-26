---
title: Docx إلى Epub
linktitle: Docx إلى Epub
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستندات Word من تنسيق Docx إلى تنسيق Epub باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /es/net/basic-conversions/docx-to-epub/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق Docx إلى تنسيق Epub. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، تحتاج إلى تهيئة ملف`Document` عن طريق توفير المسار إلى المستند المصدر بتنسيق Docx. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع مسار الدليل الفعلي حيث يوجد المستند الخاص بك ، و`"Document.docx"` باسم المستند المصدر الخاص بك. إليك مقتطف الشفرة:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## الخطوة 2: تحويل المستند إلى تنسيق Epub

 بعد ذلك ، يمكنك متابعة عملية التحويل. اتصل ب`Save` طريقة على`Document` كائن وتوفير المسار واسم الملف للمستند الناتج بتنسيق Epub. في هذا المثال ، سنحفظه باسم`"BaseConversions.DocxToEpub.epub"`. إليك مقتطف الشفرة:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");
```

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق Docx إلى تنسيق Epub باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Docx To Epub باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	doc.Save(dataDir + "BaseConversions.DocxToEpub.epub");

```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.