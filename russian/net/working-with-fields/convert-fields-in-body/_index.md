---
title: تحويل الحقول في الجسم
linktitle: تحويل الحقول في الجسم
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام Aspose.Words for .NET لتحويل حقول الصفحة إلى نص في نص مستند Word.
type: docs
weight: 10
url: /ru/net/working-with-fields/convert-fields-in-body/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنرشدك إلى كيفية استخدام ميزة ConvertFieldsInBody في Aspose.Words for .NET باستخدام كود المصدر C # المقدم. تتيح لك هذه الميزة تحويل حقول معينة في نص المستند إلى نص عادي ، مما يسهل معالجة المستندات الخاصة بك. اتبع الخطوات أدناه لاستخدام هذه الميزة بشكل فعال.

## الخطوة 1: المتطلبات الأساسية

قبل أن تبدأ ، تأكد من تثبيت Aspose.Words for .NET وأن لديك مستندًا جاهزًا للمعالجة. تأكد أيضًا من أن لديك مسار الدليل إلى مستنداتك.

## الخطوة 2: قم بتحميل المستند

ابدأ بالتصريح عن متغير للمسار إلى دليل المستندات ، ثم استخدم هذا المتغير لتهيئة كائن المستند من المستند المحدد. في مثالنا ، يُطلق على المستند اسم "Linked Field.docx".

```csharp
// المسار إلى دليل المستندات الخاص بك.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Linked fields.docx");
```

## الخطوة 3: تحويل حقول الصفحة إلى نص عادي

الآن بعد أن تم تحميل المستند ، يمكننا الانتقال إلى خطوات التحويل. لتحويل حقول الصفحة إلى نص عادي في نص القسم الأول ، يمكنك استخدام ملحق`Range.Fields` طريقة للحصول على جميع الحقول في النطاق المحدد ، ثم تصفية الحقول من النوع`FieldType.FieldPage` . ثم يمكنك استخدام ملف`ForEach` طريقة للتكرار عبر كل حقل واستدعاء`Unlink()` طريقة لتحويله إلى نص عادي.

```csharp
// قم بتمرير المعلمات المناسبة لتحويل حقول الصفحة إلى نص عادي في نص القسم الأول.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.Unlink());
```

## الخطوة 4: احفظ المستند المعدل

 بمجرد تحويل حقول الصفحة إلى نص عادي ، يمكنك حفظ المستند المعدل باستخدام امتداد`Save()` طريقة وتحديد مسار واسم ملف الإخراج. في مثالنا ، نحفظها كـ "WorkingWithFields.ConvertFieldsInBody.docx".

```csharp
// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInBody.docx");
```

### مثال على شفرة المصدر لتحويل الحقول في النص باستخدام Aspose.Words for .NET

إليك مثال شفرة المصدر الكاملة لتحويل الحقول إلى نص باستخدام Aspose.Words for .NET:

```csharp
// المسار إلى دليل المستندات الخاص بك.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "Linked fields.docx");

// قم بتمرير المعلمات المناسبة لتحويل حقول الصفحة إلى نص عادي في نص القسم الأول.
doc.FirstSection.Body.Range.Fields.Where(f => f.Type == FieldType.FieldPage).ToList().ForEach(f => f.A
