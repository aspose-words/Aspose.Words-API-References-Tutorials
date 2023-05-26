---
title: حماية كلمة المرور
linktitle: حماية كلمة المرور
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية حماية مستندات Word الخاصة بك بكلمة مرور باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/document-protection/password-protection/
---

في هذا البرنامج التعليمي ، سنوجهك عبر خطوات استخدام ميزة الحماية بكلمة مرور في Aspose.Words for .NET. تتيح لك هذه الميزة حماية مستند Word بكلمة مرور لضمان سريته. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وتطبيق الحماية

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## الخطوة الثانية: تطبيق الحماية بكلمة مرور

ثم يمكنك تطبيق الحماية بكلمة مرور باستخدام طريقة حماية () كائن المستند:

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

تأكد من استبدال كلمة المرور بكلمة المرور الفعلية التي تريد استخدامها لحماية المستند.

## الخطوة 3: حفظ المستند المحمي

أخيرًا ، يمكنك حفظ المستند المحمي باستخدام طريقة Save () لكائن Document:

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند المحمي.

### مثال على شفرة المصدر لحماية كلمة المرور باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لحماية كلمة المرور باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//تطبيق حماية المستندات.
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

تذكر استبدال "دليل المستندات" بدليل المستندات و "كلمة المرور" بكلمة المرور الفعلية التي تريد استخدامها.

