---
title: إدراج الحقول المتداخلة
linktitle: إدراج الحقول المتداخلة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج الحقول المتداخلة بسهولة في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-nested-fields/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة "إدراج الحقول المتداخلة" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستندات

في الكود المقدم، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب لدليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء المستند و DocumentBuilder

نبدأ بإنشاء مستند جديد وتهيئة DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدراج فواصل الصفحات

نستخدم حلقة لإدراج فواصل صفحات متعددة في المستند.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## الخطوة 4: الانتقال إلى التذييل

 نحن نستخدم ال`MoveToHeaderFooter()` طريقة DocumentBuilder لتحريك المؤشر إلى التذييل الرئيسي.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## الخطوة 5: إدراج الحقل المتداخل

 نحن نستخدم DocumentBuilder`InsertField()`طريقة لإدراج حقل متداخل في التذييل.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 وأخيراً نسمي`Update()` طريقة تحديث الحقل

```csharp
field. Update();
```

### نموذج التعليمات البرمجية المصدر لإدراج الحقول المتداخلة باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وDocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج فواصل الصفحات.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// الانتقال إلى التذييل.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// إدراج حقل متداخل.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// قم بتحديث الحقل.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

في هذا المثال، قمنا بإنشاء مستند جديد، وإدراج فواصل الصفحات، ونقلنا المؤشر إلى التذييل، ثم قمنا بإدراج حقل متداخل في التذييل.

### الأسئلة الشائعة

#### س: كيف يمكنني إدراج حقول متداخلة في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لإدراج حقول متداخلة في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك اتباع الخطوات التالية:

1. احصل على الفقرة التي تريد إدراج الحقول المتداخلة فيها.
2.  إنشاء`FieldStart` كائن للحقل الأصل.
3.  أضف الحقول الفرعية باستخدام`FieldStart.NextSibling` طريقة تمرير المقابلة`FieldStart` الكائنات كمعلمات.

#### س: ما هي فوائد استخدام الحقول المتداخلة في مستند Word مع Aspose.Words لـ .NET؟

ج: يوفر استخدام الحقول المتداخلة العديد من المزايا في مستند Word باستخدام Aspose.Words لـ .NET. يتيح ذلك مرونة أكبر في إنشاء قوالب المستندات الديناميكية، من خلال السماح بإدراج قيم وحسابات متغيرة في الحقول المتداخلة. يمكن أن تسهل الحقول المتداخلة أيضًا إنشاء المحتوى تلقائيًا، مثل إنشاء جداول المحتوى وأرقام الصفحات وما إلى ذلك.

#### س: هل يمكنني الحصول على حقول متداخلة متعددة المستويات في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: نعم، من الممكن وجود حقول متداخلة متعددة المستويات في مستند Word باستخدام Aspose.Words لـ .NET. يمكنك إنشاء تسلسلات هرمية معقدة للحقول المتداخلة باستخدام`FieldStart.NextSibling` طريقة لإضافة حقول فرعية إلى الحقول الأصلية الموجودة.

#### س: كيف يمكنني تخصيص خصائص الحقول المتداخلة في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: لتخصيص خصائص الحقول المتداخلة في مستند Word باستخدام Aspose.Words لـ .NET، يمكنك الوصول إلى الملف المطابق`FieldStart`الكائنات وتعديل خصائصها حسب الحاجة. يمكنك تعيين خيارات التنسيق والقيم والحسابات وما إلى ذلك للحقول المتداخلة لتحقيق النتيجة المطلوبة.

#### س: هل يؤثر إدراج الحقول المتداخلة على أداء مستند Word مع Aspose.Words لـ .NET؟

ج: يمكن أن يؤثر إدراج الحقول المتداخلة على أداء مستند Word باستخدام Aspose.Words لـ .NET، خاصة إذا كان المستند يحتوي على عدد كبير من الحقول المتداخلة أو التسلسلات الهرمية المعقدة. يوصى بتحسين التعليمات البرمجية مع تجنب العمليات غير الضرورية أو المتكررة في الحقول المتداخلة لتحسين الأداء.