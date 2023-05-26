---
title: إزالة حماية المستند
linktitle: إزالة حماية المستند
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إزالة الحماية من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/document-protection/remove-document-protection/
---

في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة المستند غير المحمي في Aspose.Words for .NET. تتيح لك هذه الميزة إزالة الحماية من مستند Word لتسهيل الوصول إليه لمزيد من التحرير. اتبع الخطوات التالية:

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
