---
title: أدخل الحقل المتقدم بدون Document Builder
linktitle: أدخل الحقل المتقدم بدون Document Builder
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج حقل متقدم في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج حقل متقدم بدون DocumentBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند والفقرة

نبدأ بإنشاء مستند جديد وجلب الفقرة الأولى.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## الخطوة 3: إدخال الحقل المتقدم

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل متقدم في الفقرة.

```csharp
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);
```

ثم نقوم بتكوين الخصائص المختلفة للحقل المتقدم من خلال تحديد القيم المطلوبة.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### مثال على الكود المصدري لإدخال حقل متقدم بدون DocumentBuilder مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// أدخل الحقل المتقدم.
FieldAdvance field = (FieldAdvance)para.AppendField(FieldType.FieldAdvance, false);

field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";

field. Update();

doc.Save(dataDir + "InsertionFieldAdvanceWithoutDocumentBuilder.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدخلنا حقلاً متقدمًا دون استخدام DocumentBuilder ، وقمنا بتكوين خصائص الحقل المختلفة ، وحفظنا المستند باسم ملف محدد.

هذا يختتم دليلنا حول كيفية استخدام ميزة "إدراج حقل متقدم بدون DocumentBuilder" مع Aspose.Words for .NET.

### التعليمات

#### س: ما هو المجال المتقدم في Aspose.Words؟

ج: حقل متقدم في Aspose. الكلمات هي نوع خاص من الحقول يسمح لك بإجراء العمليات الحسابية وتضمين الشروط وتنفيذ العمليات المعقدة في مستند Word. يوفر مرونة كبيرة لإنشاء حقول ديناميكية ومخصصة.

#### س: كيفية إدراج حقل متقدم في مستند Word دون استخدام Document Builder في Aspose.Words؟

ج: لإدراج حقل متقدم في مستند Word دون استخدام Document Builder في Aspose.Words ، يمكنك اتباع الخطوات التالية:

1. استيراد فئة المستند والحقل من Aspose.Words.Fields namespace.
2. قم بإنشاء مثيل من المستند عن طريق تحميل المستند الحالي.
3. استخدم طريقة InsertField لإدراج حقل متقدم عن طريق تحديد رمز الحقل المتقدم.
4. احفظ المستند.

#### س: كيف تحصل على نتيجة حقل متقدم في مستند Word؟

ج: للحصول على نتيجة حقل متقدم في مستند Word ، يمكنك استخدام خاصية النتيجة المتوفرة في فئة الحقل. ترجع هذه الخاصية النتيجة المحسوبة للحقل.

#### س: هل يمكنني تعديل صيغة حقل متقدم بعد إدراجه في مستند Word؟

ج: نعم ، يمكنك تعديل صيغة حقل متقدم بعد إدراجه في مستند Word. يمكنك القيام بذلك عن طريق الوصول إلى خاصية FieldCode لفئة الحقل وتحديث الصيغة عن طريق تعديل نص الصيغة.