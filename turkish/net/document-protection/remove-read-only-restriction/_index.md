---
title: إزالة قيود القراءة فقط
linktitle: إزالة قيود القراءة فقط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إزالة قيود القراءة فقط من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/document-protection/remove-read-only-restriction/
---
في هذا البرنامج التعليمي ، سنرشدك عبر خطوات استخدام ميزة إزالة قيود القراءة فقط Aspose.Words for .NET. تتيح لك هذه الميزة إزالة قيود القراءة فقط من مستند Word لجعله قابلاً للتحرير. اتبع الخطوات التالية:

## الخطوة 1: إنشاء المستند وإعداد الحماية

ابدأ بإنشاء مثيل لفئة المستند:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

قم بتعيين كلمة مرور للمستند باستخدام خاصية SetPassword () للكائن WriteProtection:

تأكد من استبدال "MyPassword" بكلمة المرور الفعلية التي استخدمتها لحماية المستند.

## الخطوة 2: إزالة قيود القراءة فقط

لإزالة تقييد القراءة فقط ، قم بتعيين الخاصية ReadOnlyRecommended إلى false:

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## الخطوة 3: تطبيق حماية غير مقيدة

أخيرًا ، قم بتطبيق حماية غير مقيدة باستخدام طريقة حماية كائن المستند:

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند بدون قيود القراءة فقط.

### مثال على شفرة المصدر الخاصة بإزالة القيود للقراءة فقط باستخدام Aspose.Words for .NET

فيما يلي شفرة المصدر الكاملة لإزالة قيود القراءة فقط باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	// أدخل كلمة مرور يصل طولها إلى 15 حرفًا.
	doc.WriteProtection.SetPassword("MyPassword");

	// قم بإزالة خيار القراءة فقط.
	doc.WriteProtection.ReadOnlyRecommended = false;

	// تطبيق الحماية ضد الكتابة دون أي حماية.
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

باتباع هذه الخطوات ، يمكنك بسهولة إزالة قيود القراءة فقط من مستند Word باستخدام Aspose.Words for .NET.

