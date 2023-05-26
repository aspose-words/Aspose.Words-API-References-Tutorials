---
title: احصل على أسماء حقول دمج المراسلات
linktitle: احصل على أسماء حقول دمج المراسلات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الحصول على أسماء حقول دمج البريد في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-fields/get-mail-merge-field-names/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "Get Merge Field Names" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة الثانية: تحميل المستند

تتمثل الخطوة الأولى في تحميل المستند حيث تريد الحصول على أسماء حقول الدمج.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

تأكد من استبدال "ملف المستند" باسم ملفك الخاص.

## الخطوة 3: احصل على أسماء حقول الدمج

 نحن نستخدم ال`GetFieldNames()` طريقة للحصول على مصفوفة تحتوي على أسماء حقول الدمج الموجودة في المستند.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 ال`fieldNames` متغير يحتوي الآن على أسماء حقول الدمج.

### مثال رمز المصدر للحصول على دمج أسماء الحقول مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// احصل على أسماء حقول الدمج.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// عرض عدد حقول الدمج.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 في هذا المثال ، قمنا بتحميل مستند ، وحصلنا على أسماء حقول الدمج باستخدام امتداد`GetFieldNames()` الطريقة ، وعرض عدد حقول الدمج الموجودة في المستند.

هذا يختتم دليلنا حول استخدام ميزة "الحصول على أسماء الحقول المدمجة" مع Aspose.Words for .NET.