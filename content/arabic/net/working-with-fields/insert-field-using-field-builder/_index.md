---
title: إدراج حقل باستخدام منشئ الحقول
linktitle: إدراج حقل باستخدام منشئ الحقول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقول مخصصة في مستندات Word الخاصة بك باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-field-using-field-builder/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة "إدراج حقل باستخدام FieldBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستندات

في الكود المقدم، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب لدليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء الوثيقة

نبدأ بإنشاء مستند جديد.

```csharp
Document doc = new Document();
```

## الخطوة 3: إنشاء حقل IF باستخدام FieldBuilder

نستخدم فئة FieldBuilder لإنشاء حقل IF بحقلين MERGEFIELD متداخلين. في هذا المثال، يعرض الحقل IF الاسم الأول والأخير بناءً على الشرط.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## الخطوة 4: إدراج حقل IF في المستند

 نحن نستخدم ال`BuildAndInsert()` طريقة لإنشاء حقل IF وإدراجه في موقع محدد في المستند.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### مثال على التعليمات البرمجية المصدر لإدراج حقل باستخدام FieldBuilder مع Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();

// بناء حقل IF باستخدام FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// أدخل الحقل IF في المستند.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

في هذا المثال، قمنا بإنشاء مستند جديد، وقمنا بإنشاء حقل IF باستخدام حقول MERGEFIELD المتداخلة، ثم قمنا بإدراج هذا الحقل في المستند في موقع محدد. ثم يتم حفظ المستند باسم ملف محدد.

### الأسئلة الشائعة

#### س: ما هو مُنشئ الحقل في Aspose.Words؟

ج: يعد منشئ الحقول في Aspose.Words أداة قوية لإنشاء الحقول ومعالجتها في مستند Word. وهو يوفر ميزات متقدمة لإنشاء الحقول وتخصيصها، بما في ذلك إدراج رموز الحقول وإدارة خيارات التنسيق.

#### س: ما أنواع الحقول التي يمكن إدراجها باستخدام منشئ الحقول؟

ج: يسمح لك منشئ الحقول في Aspose.Words بإدراج أنواع مختلفة من الحقول في مستند Word. فيما يلي بعض الأمثلة على أنواع الحقول شائعة الاستخدام:

- MERGEFIELD: يستخدم لدمج البيانات من مصادر خارجية.
- التاريخ: يعرض التاريخ الحالي.
- PAGE: يعرض رقم الصفحة الحالية.
- IF: يسمح بتكييف عرض المحتوى وفقًا للشرط.
- جدول المحتويات: يقوم تلقائيًا بإنشاء جدول محتويات استنادًا إلى أنماط عنوان المستند.

#### س: كيفية تخصيص الحقول المدرجة باستخدام منشئ الحقول؟

ج: يقدم منشئ الحقول خيارات التخصيص للحقول المدرجة. يمكنك استخدام أساليب وخصائص منشئ الحقل لتعيين خيارات مثل تنسيق الحقل والوسائط والمفاتيح والقيم الافتراضية. على سبيل المثال، يمكنك تعيين تنسيق التاريخ، وتنسيق الأرقام، وفاصل الآلاف، وما إلى ذلك.
  