---
title: قم بإدراج FieldIncludeText بدون Document Builder
linktitle: قم بإدراج FieldIncludeText بدون Document Builder
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقل FieldIncludeText في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-field-include-text-without-document-builder/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح كود مصدر C # أدناه ، والذي يستخدم وظيفة "إدراج حقل FieldIncludeText" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: إدراج حقل FieldIncludeText

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل FieldIncludeText في الفقرة.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

ثم نقوم بتكوين خصائص حقل FieldIncludeText عن طريق تحديد اسم الإشارة المرجعية واسم الملف المصدر.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

بعد ذلك ، نضيف الفقرة إلى نص المستند.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
fieldIncludeText.Update();
```

### مثال على شفرة المصدر لإدخال حقل FieldIncludeText مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند والفقرة.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// أدخل الحقل FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأعدنا فقرة ، وأدخلنا FieldIncludeTexten يحدد اسم الإشارة المرجعية واسم الملف المصدر ، وحفظنا المستند باسم ملف محدد.

بهذا يختتم دليلنا حول استخدام ميزة "Insert a FieldIncludeText" مع Aspose.Words for .NET.