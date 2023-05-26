---
title: أدخل حقل TOA بدون Document Builder
linktitle: أدخل حقل TOA بدون Document Builder
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإدخال حقل TOA بدون Document Builder باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-fields/insert-toafield-without-document-builder/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "TOA Field Insertion" في Aspose.Words for .NET. اتبع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند والفقرة

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

## الخطوة 4: إضافة الفقرة إلى نص المستند

نضيف الفقرة التي تحتوي على حقل TA إلى نص المستند.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## الخطوة 5: إنشاء فقرة لحقل TOA

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

## الخطوة 7: إضافة الفقرة إلى نص المستند

نضيف الفقرة التي تحتوي على حقل TOA إلى نص المستند.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## الخطوة 8: تحديث TOA Field

 أخيرًا ، نسمي`Update()` طريقة لتحديث حقل TOA.

```csharp
fieldToa.Update();
```

### مثال على رمز المصدر لإدخال حقل TOA بدون Document Builder مع Aspose.Words for .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// نريد إدخال حقول TA و TOA مثل هذا:
// {TA \ c 1 \ l "القيمة 0"}
// {TOA \ c 1}

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
