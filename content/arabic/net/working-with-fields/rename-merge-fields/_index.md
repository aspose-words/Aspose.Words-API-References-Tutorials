---
title: إعادة تسمية حقول الدمج
linktitle: إعادة تسمية حقول الدمج
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: ستتعلم في هذا البرنامج التعليمي كيفية إعادة تسمية حقول الدمج في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/rename-merge-fields/
---

فيما يلي دليل خطوة بخطوة لشرح كود مصدر C# أدناه والذي يستخدم ميزة إعادة تسمية حقل الدمج في Aspose.Words for .NET. اتبع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستندات

في الكود المقدم، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب لدليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند وإدراج حقول الدمج

نبدأ بإنشاء مستند جديد واستخدام ملف`DocumentBuilder` لإدراج حقول الدمج.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## الخطوة 3: إعادة تسمية حقول الدمج

نقوم بالتكرار خلال كل حقل في نطاق المستند، وإذا كان حقل دمج، فإننا نعيد تسمية الحقل عن طريق إضافة "_"إعادة تسمية" لاحقة.

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## الخطوة 4: حفظ الوثيقة

 وأخيراً نسمي`Save()` طريقة حفظ الوثيقة المعدلة.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### مثال على التعليمات البرمجية المصدر لإعادة تسمية حقول الدمج باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وأدخل حقول الدمج.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// إعادة تسمية حقول الدمج.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// احفظ المستند.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

اتبع هذه الخطوات لإعادة تسمية حقول الدمج في مستندك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة

#### س: كيف يمكنني إعادة تسمية الحقول المدمجة في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: لإعادة تسمية الحقول المدمجة في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك تكرار الحقول الموجودة في المستند باستخدام الأمر`FieldMergingArgs` الصف واستخدام`FieldMergingArgs.FieldName` طريقة إعادة تسمية الحقل

#### س: هل من الممكن إعادة تسمية بعض الحقول المدمجة فقط في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: نعم، من الممكن إعادة تسمية بعض الحقول المدمجة فقط في مستند Word باستخدام Aspose.Words لـ .NET. يمكنك تصفية الحقول التي تريد إعادة تسميتها باستخدام معايير محددة، مثل اسم الحقل أو الخصائص الأخرى ذات الصلة. ثم يمكنك إعادة تسمية الحقول المقابلة باستخدام`FieldMergingArgs.FieldName` طريقة.

#### س: كيف يمكنني التحقق من إعادة تسمية الحقل المدمج بنجاح في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للتحقق من إعادة تسمية الحقل المدمج بنجاح في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام`FieldMergedArgs` الصف والوصول إلى`FieldMergedArgs.IsMerged` الخاصية لتحديد ما إذا كان قد تمت إعادة تسمية الحقل بالنقر فوق.

#### س: ما هي النتائج المترتبة على إعادة تسمية حقل مدمج في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: عند إعادة تسمية حقل مدمج في مستند Word باستخدام Aspose.Words لـ .NET، فإنه يغير اسم الحقل في المستند، مما قد يؤثر على وظائف أو عمليات أخرى تعتمد على اسم الحقل. تأكد من مراعاة هذه العواقب المحتملة قبل إعادة تسمية الحقول المدمجة.

#### س: هل من الممكن استعادة الاسم الأصلي للحقل المدمج بعد إعادة تسميته باستخدام Aspose.Words for .NET؟

ج: نعم، من الممكن استعادة الاسم الأصلي للحقل المدمج بعد إعادة تسميته باستخدام Aspose.Words for .NET. يمكنك تخزين الاسم الأصلي للحقل في متغير أو قائمة، ثم استخدام تلك المعلومات لاستعادة الاسم الأصلي إذا لزم الأمر.