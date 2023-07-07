---
title: إعادة تسمية حقول الدمج
linktitle: إعادة تسمية حقول الدمج
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، ستتعلم كيفية إعادة تسمية حقول الدمج في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/rename-merge-fields/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود المصدر C # أدناه والذي يستخدم ميزة إعادة تسمية حقل الدمج في Aspose.Words for .NET. اتبع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

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

نقوم بإجراء حلقة عبر كل حقل في نطاق المستند ، وإذا كان حقل دمج ، فإننا نعيد تسمية الحقل عن طريق إضافة "_أعيدت تسميته "لاحقة.

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

## الخطوة 4: حفظ المستند

 أخيرًا ، نسمي`Save()` طريقة لحفظ المستند المعدل.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### مثال على رمز المصدر لإعادة تسمية حقول الدمج باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وإدراج حقول الدمج.
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

### التعليمات

#### س: كيف يمكنني إعادة تسمية الحقول المدمجة في مستند Word باستخدام Aspose.Words for .NET؟

 ج: لإعادة تسمية الحقول المدمجة في مستند Word باستخدام Aspose.Words for .NET ، يمكنك تكرار الحقول في المستند باستخدام`FieldMergingArgs` فئة واستخدام`FieldMergingArgs.FieldName` طريقة لإعادة تسمية المجال.

#### س: هل من الممكن إعادة تسمية بعض الحقول المدمجة فقط في مستند Word باستخدام Aspose.Words for .NET؟

ج: نعم ، من الممكن إعادة تسمية بعض الحقول المدمجة فقط في مستند Word باستخدام Aspose.Words for .NET. يمكنك تصفية الحقول المراد إعادة تسميتها باستخدام معايير محددة ، مثل اسم الحقل أو الخصائص الأخرى ذات الصلة. ثم يمكنك إعادة تسمية الحقول المقابلة باستخدام امتداد`FieldMergingArgs.FieldName` طريقة.

#### س: كيف يمكنني التحقق مما إذا تمت إعادة تسمية حقل مدمج بنجاح في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للتحقق مما إذا تمت إعادة تسمية حقل مدمج بنجاح في مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام`FieldMergedArgs` الطبقة والوصول إلى`FieldMergedArgs.IsMerged` لتحديد ما إذا تمت إعادة تسمية الحقل بالقيمة.

#### س: ما هي النتائج المترتبة على إعادة تسمية حقل مدمج في مستند Word باستخدام Aspose.Words for .NET؟

ج: عند إعادة تسمية حقل مدمج في مستند Word باستخدام Aspose.Words for .NET ، فإنه يغير اسم الحقل في المستند ، مما قد يؤثر على الوظائف أو العمليات الأخرى التي تعتمد على اسم الحقل. تأكد من مراعاة هذه النتائج المحتملة قبل إعادة تسمية الحقول المدمجة.

#### س: هل من الممكن استعادة الاسم الأصلي للحقل المدمج بعد إعادة تسميته باستخدام Aspose.Words for .NET؟

ج: نعم ، من الممكن استعادة الاسم الأصلي للحقل المدمج بعد إعادة تسميته باستخدام Aspose.Words for .NET. يمكنك تخزين الاسم الأصلي للحقل في متغير أو قائمة ، ثم استخدام هذه المعلومات لاستعادة الاسم الأصلي إذا لزم الأمر.