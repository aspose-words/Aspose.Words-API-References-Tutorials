---
title: أدخل الحقل
linktitle: أدخل الحقل
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقل في مستندات Word باستخدام Aspose.Words for .NET. إضفاء الطابع الشخصي على المستندات الخاصة بك مع الحقول الديناميكية.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-field/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح شفرة المصدر C # أدناه ، والتي تستخدم ميزة "إدراج حقل" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مستند و DocumentBuilder

نبدأ بإنشاء مستند جديد وتهيئة DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدخال الحقل

 نحن نستخدم ال`InsertField()` طريقة DocumentBuilder لإدراج حقل في المستند. في هذا المثال ، نقوم بإدخال حقل دمج (MERGEFIELD) مع اسم الحقل "MyFieldName" وتنسيق الدمج.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### مثال على الكود المصدري لإدخال حقل باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند و DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل الحقل.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأعدنا تهيئة DocumentBuilder ، ثم قمنا بإدراج حقل دمج باسم الحقل "MyFieldName" وتنسيق الدمج. ثم يتم حفظ المستند باسم ملف محدد.

بهذا نختتم دليلنا حول استخدام ميزة "إدراج حقل" مع Aspose.Words for .NET.
