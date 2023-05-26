---
title: إعادة تسمية حقول الدمج
linktitle: إعادة تسمية حقول الدمج
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، ستتعلم كيفية إعادة تسمية حقول الدمج في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /it/net/working-with-fields/rename-merge-fields/
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