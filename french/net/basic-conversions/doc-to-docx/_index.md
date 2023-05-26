---
title: Doc إلى Docx
linktitle: Doc إلى Docx
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستندات Word من تنسيق doc. إلى تنسيق Docx باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /fr/net/basic-conversions/doc-to-docx/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لاستخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق .doc إلى تنسيق Docx. سنشرح الكود المصدري C # المقدم ونوجهك حول كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة الأولى: تهيئة البيئة التنموية

قبل أن تبدأ في البرمجة ، تأكد من أن لديك بيئة تطوير مناسبة. افتح Visual Studio أو C # IDE المفضل لديك وقم بإنشاء مشروع جديد.

## الخطوة 2: إضافة المراجع واستيراد مساحات الأسماء

لاستخدام Aspose.Words for .NET ، تحتاج إلى إضافة مراجع إلى المكتبة في مشروعك. انقر بزر الماوس الأيمن على مجلد المراجع في مشروعك ، وحدد "إضافة مرجع" ، واستعرض الموقع حيث قمت بتثبيت مكتبة Aspose.Words for .NET. حدد الإصدار المناسب وانقر على "موافق" لإضافة المرجع.

بعد ذلك ، قم باستيراد مساحات الأسماء الضرورية أعلى ملف C # الخاص بك:

```csharp
using Aspose.Words;
```

## الخطوة 3: تهيئة كائن المستند

 في هذه الخطوة ، ستقوم بتهيئة ملف`Document` مع المسار إلى المستند المصدر بتنسيق doc. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع مسار الدليل الفعلي حيث يوجد المستند الخاص بك ، و`"Document.doc"` باسم المستند المصدر الخاص بك. إليك مقتطف الشفرة:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.doc");
```

## الخطوة 4: تحويل المستند إلى تنسيق Docx

 الآن بعد أن قمت بتهيئة ملف`Document`كائن ، يمكنك متابعة عملية التحويل. يوفر Aspose.Words for .NET خيارات وإعدادات متنوعة للتخصيص ، ولكن للتحويل الأساسي ، لا يلزم وجود معلمات إضافية.

## الخطوة 5: حفظ المستند المحول

 لحفظ المستند المحول بتنسيق Docx ، تحتاج إلى استدعاء ملف`Save` طريقة على`Document` هدف. قم بتوفير المسار واسم الملف للمستند الناتج. في هذا المثال ، سنحفظه باسم`"BaseConversions.DocToDocx.docx"`. إليك مقتطف الشفرة:

```csharp
doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
```

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق .doc إلى تنسيق Docx باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Doc To Docx باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.doc");

	doc.Save(dataDir + "BaseConversions.DocToDocx.docx");
	
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.




