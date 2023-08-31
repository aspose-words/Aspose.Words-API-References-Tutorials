---
title: أدخل حقل TOA بدون أداة إنشاء المستندات
linktitle: أدخل حقل TOA بدون أداة إنشاء المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإدراج حقل TOA بدون Document Builder باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-toafield-without-document-builder/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة "TOA Field Insertion" في Aspose.Words for .NET. اتبع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستندات

في الكود المقدم، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب لدليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء الوثيقة والفقرة

نبدأ بإنشاء مستند جديد وتهيئة فقرة.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## الخطوة 3: إدخال حقل TA

نستخدم فئة FieldTA لإدراج حقل TA في الفقرة.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## الخطوة 4: إضافة الفقرة إلى نص الوثيقة

نضيف الفقرة التي تحتوي على حقل TA إلى نص الوثيقة.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## الخطوة 5: إنشاء الفقرة لحقل TOA

نقوم بإنشاء فقرة جديدة لحقل TOA.

```csharp
para = new Paragraph(doc);
```

## الخطوة 6: إدخال حقل TOA

نستخدم فئة FieldToa لإدراج حقل TOA في الفقرة.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## الخطوة 7: إضافة الفقرة إلى نص الوثيقة

نضيف الفقرة التي تحتوي على حقل TOA إلى نص المستند.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## الخطوة 8: تحديث حقل TOA

 وأخيراً نسمي`Update()` طريقة تحديث حقل TOA.

```csharp
fieldToa.Update();
```

### مثال على التعليمات البرمجية المصدر لإدراج حقل TOA بدون Document Builder باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// نريد إدراج حقلي TA وTOA مثل هذا:
// { تا \c 1 \l "القيمة 0" }
// { توا \ج 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### الأسئلة الشائعة

#### س: كيفية تخصيص مظهر حقل TOA المدرج في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: يمكنك تخصيص مظهر حقل TOA المدرج باستخدام خصائص ملف`FieldTOA` كائن لتحديد خيارات التنسيق.

#### س: هل يمكنني إضافة حقول TOA متعددة في مستند Word واحد باستخدام Aspose.Words لـ .NET؟

ج: نعم، يمكنك إضافة حقول TOA متعددة في مستند Word واحد باستخدام Aspose.Words لـ .NET. فقط كرر خطوات الإدراج لكل حقل.

#### س: كيف يمكنني التحقق من إدراج حقل TOA بنجاح في مستند Word باستخدام Aspose.Words for .NET؟

ج: للتحقق من إدراج حقل TOA بنجاح، يمكنك تصفح محتوى المستند والبحث عن مثيلات حقل TOA.

#### س: هل يؤثر إدراج حقل TOA بدون استخدام DocumentBuilder على تنسيق مستند Word باستخدام Aspose.Words لـ .NET؟

ج: إن إدراج حقل TOA بدون استخدام DocumentBuilder لا يؤثر بشكل مباشر على تنسيق مستند Word. ومع ذلك، يمكن أن تؤثر خيارات تنسيق حقل TOA على التنسيق العام للمستند.