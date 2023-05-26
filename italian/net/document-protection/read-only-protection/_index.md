---
title: قراءة الحماية فقط
linktitle: قراءة الحماية فقط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية حماية مستندات Word للقراءة فقط باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/document-protection/read-only-protection/
---
في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة الحماية للقراءة فقط في Aspose.Words for .NET. تتيح لك هذه الميزة جعل مستند Word للقراءة فقط لمنع التعديل غير المصرح به. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وتطبيق الحماية

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: اكتب المحتوى إلى المستند
استخدم كائن DocumentBuilder لكتابة محتوى إلى المستند:

```csharp
builder.Write("Open document as read-only");
```

## الخطوة 3: تعيين كلمة المرور وجعل المستند للقراءة فقط

قم بتعيين كلمة مرور للمستند باستخدام خاصية SetPassword () للكائن WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

تأكد من استبدال "MyPassword" بكلمة المرور الفعلية التي تريد استخدامها.

## الخطوة 4: تطبيق وثيقة للقراءة فقط

اجعل المستند للقراءة فقط عن طريق تعيين الخاصية ReadOnlyRecommended على true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## الخطوة 5: تطبيق الحماية للقراءة فقط وحفظ المستند

أخيرًا ، قم بتطبيق الحماية للقراءة فقط باستخدام طريقة Protect () لكائن المستند:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند المحمي.

### مثال على شفرة المصدر للحماية للقراءة فقط باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للحماية للقراءة فقط باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	// أدخل كلمة مرور يصل طولها إلى 15 حرفًا.
	doc.WriteProtection.SetPassword("MyPassword");

	// اجعل المستند للقراءة فقط.
	doc.WriteProtection.ReadOnlyRecommended = true;

	// تطبيق الحماية ضد الكتابة للقراءة فقط.
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

باتباع هذه الخطوات ، يمكنك حماية مستنداتك بسهولة

