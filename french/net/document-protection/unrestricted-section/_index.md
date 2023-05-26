---
title: قسم غير مقيد
linktitle: قسم غير مقيد
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديد الأقسام غير المقيدة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/document-protection/unrestricted-section/
---

في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة القسم غير المقيد في Aspose.Words for .NET. تتيح لك هذه الميزة تحديد أقسام معينة في مستند Word غير محمية ، حتى إذا كان باقي المستند محميًا. اتبع الخطوات التالية:

## الخطوة الأولى: إنشاء المستند والأقسام

ابدأ بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أضف محتوى إلى المستند
استخدم كائن DocumentBuilder لإضافة محتوى إلى المستند وإدراج فواصل المقاطع:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## الخطوة 3: حماية المستند والأقسام

تعمل حماية القسم فقط عندما يتم تمكين حماية المستند ولا يُسمح إلا بالتحرير في حقول النموذج. يمكنك حماية المستند باستخدام طريقة Protect () الخاصة بكائن المستند:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

تأكد من تحديد نوع الحماية الصحيح وتعيين كلمة المرور المطلوبة.

## الخطوة 4: تعطيل الحماية لقسم معين

بشكل افتراضي ، تكون جميع الأقسام محمية ، ولكن يمكنك تعطيل الحماية بشكل انتقائي لقسم معين باستخدام خاصية ProtectedForForms الخاصة بكائن القسم:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

في هذا المثال ، تم تعطيل الحماية للقسم الأول.

## الخطوة 5: احفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند بأقسام غير مقيدة.

### مثال على شفرة المصدر للقسم غير المقيد باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للقسم غير المقيد باستخدام Aspose.Words for .NET:


```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// أدخل قسمين مع بعض النص.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// تعمل حماية القسم فقط عندما يتم تشغيل حماية المستند ولا يُسمح إلا بالتحرير في حقول النموذج.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// بشكل افتراضي ، تكون جميع الأقسام محمية ، ولكن يمكننا إيقاف الحماية بشكل انتقائي.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

باتباع هذه الخطوات ، ستتمكن بسهولة من تحديد الأقسام غير المقيدة في مستند Word الخاص بك باستخدام Aspose.Words for .NET.

