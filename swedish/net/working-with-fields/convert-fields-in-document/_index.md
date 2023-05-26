---
title: تحويل الحقول في المستند
linktitle: تحويل الحقول في المستند
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتحويل حقول المستند إلى نص باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/convert-fields-in-document/
---

في هذا البرنامج التعليمي ، سنوجهك دليلًا خطوة بخطوة باستخدام وظيفة ConvertFieldsInDocument في Aspose.Words لبرنامج .NET. سنشرح بالتفصيل الكود المصدري C # اللازم لهذه الميزة ونقدم عينة من تنسيقات إخراج تخفيض السعر.

## الخطوة 1: المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك ما يلي:

- Aspose.Words for .NET مثبتة على جهاز التطوير الخاص بك.
- مستند Word يحتوي على حقول مرتبطة تريد تحويلها إلى نص.
- دليل مستند حيث يمكنك حفظ المستند المحول.

## الخطوة الثانية: تهيئة البيئة
تأكد من تكوين بيئة التطوير الخاصة بك بشكل صحيح لاستخدام Aspose.Words لـ .NET. قم باستيراد مساحات الأسماء الضرورية وقم بتعيين المسار إلى دليل المستندات.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 3: قم بتحميل المستند
 استخدم ال`Document` class of Aspose.Words لتحميل مستند Word الذي يحتوي على الحقول المرتبطة التي تريد تحويلها.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## الخطوة 4: تحويل الحقول المرتبطة إلى نص
 استخدم ال`Unlink()` طريقة لتحويل جميع حقول النوع "IF" التي تمت مواجهتها في المستند إلى نص. تُستخدم هذه الطريقة لتحويل الحقول المرتبطة إلى محتوى نصي.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## الخطوة 5: احفظ المستند المحول
 استخدم ال`Save()` طريقة لحفظ المستند مع الحقول المحولة إلى نص في دليل المستند المحدد.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## نموذج التعليمات البرمجية المصدر لـ ConvertFieldsInDocument باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل لوظيفة ConvertFieldsInDocument:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// قم بتمرير المعلمات المناسبة لتحويل جميع حقول IF التي تمت مواجهتها في المستند (بما في ذلك الرؤوس والتذييلات) إلى نص.
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// احفظ المستند مع الحقول التي تم تحويلها إلى قرص
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## خاتمة
تعد وظيفة Aspose.Words for .NET's ConvertFieldsInDocument وظيفة أداة قوية لتحويل الحقول المرتبطة في مستند Word إلى نص. 