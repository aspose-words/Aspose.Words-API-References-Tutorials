---
title: كود الحقل
linktitle: كود الحقل
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة للحصول على رمز الحقل والنتيجة الميدانية في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/field-code/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "Get Field Code" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة الثانية: تحميل المستند

تتمثل الخطوة الأولى في تحميل المستند حيث تريد الحصول على رموز الحقول.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

تأكد من استبدال "Hyperlinks.docx" باسم الملف الخاص بك.

## الخطوة 3: تصفح حقول المستندات

 نحن نستخدم`foreach` حلقة للتكرار خلال جميع الحقول الموجودة في المستند.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 في كل تكرار للحلقة ، نحصل على رمز الحقل باستخدام`GetFieldCode()` طريقة. نقوم أيضًا بتخزين نتيجة الحقل في متغير.

### مثال رمز المصدر للحصول على رمز الحقل مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// حلقة من خلال حقول الوثيقة.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // افعل شيئًا مع رمز الحقل والنتيجة.
}
```

في هذا المثال ، قمنا بتحميل مستند ثم تدويره عبر جميع الحقول الموجودة في المستند. في كل تكرار ، حصلنا على الكود ونتيجة الحقل. يمكنك إضافة منطقك الخاص لمعالجة الكود وحقول النتائج حسب الحاجة.

بهذا ينتهي دليلنا حول استخدام ميزة "Get Field Code" مع Aspose.Words for .NET.