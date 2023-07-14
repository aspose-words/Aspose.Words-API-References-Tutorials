---
title: إزالة حماية المستند في مستند Word
linktitle: إزالة حماية المستند في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إزالة الحماية في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-protection/remove-document-protection/
---
في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة المستند غير المحمي في Aspose.Words for .NET. تتيح لك هذه الميزة إزالة الحماية في مستند Word لجعله متاحًا لمزيد من التحرير. اتبع الخطوات التالية:

## الخطوة الأولى: إنشاء المستند وإضافة المحتوى

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أضف محتوى إلى المستند

استخدم كائن DocumentBuilder لإضافة محتوى إلى المستند:

```csharp
builder.Writeln("Text added to a document.");
```

## الخطوة 3: إلغاء حماية المستند

لإلغاء حماية المستند ، يمكنك استخدام طريقة Unprotect () لكائن المستند. يمكنك اختيار إزالة الحماية بدون كلمة مرور أو بكلمة مرور صحيحة. إزالة الحماية بدون كلمة مرور:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

تأكد من استبدال "newPassword" بكلمة مرور المستند الصحيحة.

## الخطوة 4: احفظ المستند بدون حماية

أخيرًا ، احفظ المستند بدون حماية باستخدام طريقة Save () لكائن Document:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند بدون حماية.

### مثال على شفرة المصدر لإزالة حماية المستند باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لإلغاء حماية المستند باستخدام Aspose.Words for .NET:

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// يمكن إزالة الحماية للمستندات إما بدون كلمة مرور أو باستخدام كلمة المرور الصحيحة.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

باتباع هذه الخطوات ، يمكنك بسهولة إزالة الحماية من مستند Word باستخدام Aspose.Words for .NET.

## خاتمة

في هذا البرنامج التعليمي ، اكتشفنا كيفية إزالة حماية المستندات في مستند Word باستخدام Aspose.Words for .NET. باتباع الخطوات المقدمة ، يمكنك بسهولة إلغاء حماية مستند وجعله متاحًا لمزيد من التحرير. يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية تسمح لك بمعالجة إعدادات حماية المستندات وتخصيص مستوى الأمان لمستندات Word الخاصة بك. تمنحك إزالة حماية المستند المرونة لتعديل محتوى المستند وتنسيقه حسب الحاجة.

### الأسئلة الشائعة حول إزالة حماية المستند في مستند Word

#### س: ما هي حماية المستندات في Aspose.Words for .NET؟

ج: تشير حماية المستندات في Aspose.Words for .NET إلى الميزة التي تتيح لك تطبيق إجراءات الأمان على مستند Word لتقييد التحرير والتنسيق وتعديلات المحتوى. يساعد على ضمان سلامة الوثيقة وسريتها.

#### س: كيف يمكنني إزالة حماية المستندات باستخدام Aspose.Words for .NET؟

ج: لإزالة حماية المستندات باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:
1.  قم بإنشاء مثيل لـ`Document` فئة وأ`DocumentBuilder` هدف.
2.  استخدم ال`DocumentBuilder` لإضافة محتوى إلى المستند.
3.  اتصل ب`Unprotect` طريقة`Document` كائن لإزالة أي حماية موجودة من المستند. يمكن القيام بذلك بدون كلمة مرور أو عن طريق توفير كلمة المرور الصحيحة.
4.  احفظ المستند غير المحمي باستخدام ملف`Save` طريقة`Document` هدف.

#### س: هل يمكنني إزالة الحماية من مستند Word بدون كلمة مرور؟

 ج: نعم ، يمكنك إزالة الحماية من مستند Word بدون كلمة مرور باستخدام Aspose.Words for .NET. من خلال استدعاء`Unprotect` طريقة`Document`بدون توفير كلمة مرور ، يمكنك إزالة الحماية من المستند إذا كان محميًا مسبقًا بدون كلمة مرور.

#### س: كيف يمكنني إزالة الحماية من مستند Word بكلمة مرور؟

 ج: لإزالة الحماية من مستند Word المحمي بكلمة مرور ، تحتاج إلى توفير كلمة المرور الصحيحة عند استدعاء`Unprotect` طريقة`Document` هدف. هذا يضمن أن المستخدمين الذين لديهم كلمة مرور صحيحة فقط يمكنهم إزالة الحماية والوصول إلى المستند لتحريره.

#### س: هل يمكنني إزالة أنواع حماية معينة من مستند Word؟

 ج: نعم ، باستخدام Aspose.Words for .NET ، يمكنك بشكل انتقائي إزالة أنواع حماية معينة من مستند Word. من خلال استدعاء`Unprotect` طريقة`Document` كائن ، يمكنك إزالة نوع الحماية المطلوب ، مثل الحماية للقراءة فقط أو حماية النموذج ، مع ترك أنواع الحماية الأخرى كما هي.