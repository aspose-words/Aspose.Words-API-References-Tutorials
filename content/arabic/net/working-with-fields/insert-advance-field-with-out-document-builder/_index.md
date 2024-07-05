---
title: إدراج حقل متقدم بدون أداة إنشاء المستندات
linktitle: إدراج حقل متقدم بدون أداة إنشاء المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقل متقدم في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-advance-field-with-out-document-builder/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة "إدراج الحقل المتقدم بدون DocumentBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستندات

في الكود المقدم، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب لدليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء الوثيقة والفقرة

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

نقوم بعد ذلك بتكوين الخصائص المختلفة للحقل المتقدم عن طريق تحديد القيم المطلوبة.

```csharp
field. DownOffset = "10";
field. LeftOffset = "10";
field. RightOffset = "-3.3";
field. UpOffset = "0";
field.HorizontalPosition = "100";
field. VerticalPosition = "100";
```

 وأخيراً نسمي`Update()` طريقة تحديث الحقل

```csharp
field. Update();
```

### مثال على الكود المصدري لإدراج حقل متقدم بدون DocumentBuilder مع Aspose.Words لـ .NET

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

في هذا المثال، قمنا بإنشاء مستند جديد، وإدراج حقل متقدم دون استخدام DocumentBuilder، وقمنا بتكوين خصائص الحقل المتنوعة، وحفظنا المستند باسم ملف محدد.

بهذا نختتم دليلنا حول كيفية استخدام ميزة "إدراج حقل متقدم بدون DocumentBuilder" مع Aspose.Words for .NET.

### الأسئلة الشائعة

#### س: ما هو المجال المتقدم في Aspose.Words؟

ج: الحقل المتقدم في Aspose.Words هو نوع خاص من الحقول يسمح لك بإجراء العمليات الحسابية وتضمين الشروط وإجراء عمليات معقدة في مستند Word. فهو يوفر مرونة كبيرة لإنشاء حقول ديناميكية ومخصصة.

#### س: كيفية إدراج حقل متقدم في مستند Word دون استخدام Document Builder في Aspose.Words؟

ج: لإدراج حقل متقدم في مستند Word دون استخدام Document Builder في Aspose.Words، يمكنك اتباع الخطوات التالية:

1. قم باستيراد فئة المستند والحقل من مساحة الاسم Aspose.Words.Fields.
2. قم بإنشاء مثيل للمستند عن طريق تحميل المستند الموجود لديك.
3. استخدم أسلوب InsertField لإدراج حقل متقدم عن طريق تحديد رمز الحقل المتقدم.
4. احفظ المستند.

#### س: كيف يمكن الحصول على نتيجة حقل متقدم في مستند Word؟

ج: للحصول على نتيجة حقل متقدم في مستند Word، يمكنك استخدام خاصية النتيجة المتوفرة في فئة الحقل. تقوم هذه الخاصية بإرجاع النتيجة المحسوبة للحقل.

#### س: هل يمكنني تعديل صيغة حقل متقدم بعد إدراجه في مستند Word؟

ج: نعم، يمكنك تعديل صيغة الحقل المتقدم بعد إدراجه في مستند Word. يمكنك القيام بذلك عن طريق الوصول إلى خاصية FieldCode الخاصة بفئة الحقل وتحديث الصيغة عن طريق تعديل نص الصيغة.