---
title: أدخل الحقول المتداخلة
linktitle: أدخل الحقول المتداخلة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج الحقول المتداخلة بسهولة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-nested-fields/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج الحقول المتداخلة" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: إدراج فواصل الصفحات

نستخدم حلقة لإدراج عدة فواصل صفحات في المستند.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## الخطوة 4: الانتقال إلى التذييل

 نحن نستخدم ال`MoveToHeaderFooter()` أسلوب DocumentBuilder لتحريك المؤشر إلى التذييل الرئيسي.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## الخطوة 5: إدخال الحقل المتداخل

 نحن نستخدم برنامج DocumentBuilder`InsertField()`طريقة لإدراج حقل متداخل في التذييل.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### نموذج التعليمات البرمجية المصدر لإدخال الحقول المتداخلة مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند و DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل فواصل الصفحات.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// الانتقال إلى التذييل.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// أدخل الحقل المتداخل.
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

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدرجنا فواصل الصفحات ، وحركنا المؤشر إلى التذييل ، ثم أدرجنا حقلاً متداخلًا في التذييل.

### التعليمات

#### س: كيف يمكنني إدراج الحقول المتداخلة في مستند Word باستخدام Aspose.Words for .NET؟

ج: لإدراج الحقول المتداخلة في مستند Word باستخدام Aspose.Words for .NET ، يمكنك اتباع الخطوات التالية:

1. احصل على الفقرة حيث تريد إدراج الحقول المتداخلة.
2.  إنشاء`FieldStart` كائن للحقل الأصل.
3.  أضف الحقول الفرعية باستخدام`FieldStart.NextSibling` طريقة تمرير المقابلة`FieldStart` الكائنات كمعلمات.

#### س: ما هي فوائد استخدام الحقول المتداخلة في مستند Word مع Aspose.Words for .NET؟

ج: يوفر استخدام الحقول المتداخلة العديد من المزايا في مستند Word مع Aspose.Words for .NET. يتيح ذلك مزيدًا من المرونة في إنشاء قوالب مستندات ديناميكية ، من خلال السماح بإدراج القيم المتغيرة والحسابات في الحقول المتداخلة. يمكن للحقول المتداخلة أيضًا تسهيل إنشاء المحتوى تلقائيًا ، مثل إنشاء جداول المحتوى وأرقام الصفحات وما إلى ذلك.

#### س: هل يمكنني الحصول على حقول متداخلة متعددة المستويات في مستند Word باستخدام Aspose.Words for .NET؟

 ج: نعم ، من الممكن أن يكون لديك حقول متداخلة متعددة المستويات في مستند Word باستخدام Aspose.Words for .NET. يمكنك إنشاء تسلسلات هرمية معقدة للحقول المتداخلة باستخدام ملف`FieldStart.NextSibling` طريقة لإضافة الحقول الفرعية إلى الحقول الأصل الموجودة.

#### س: كيف يمكنني تخصيص خصائص الحقول المتداخلة في مستند Word باستخدام Aspose.Words for .NET؟

 ج: لتخصيص خصائص الحقول المتداخلة في مستند Word باستخدام Aspose.Words for .NET ، يمكنك الوصول إلى ملف`FieldStart`الكائنات وتعديل خصائصها حسب الحاجة. يمكنك تعيين خيارات التنسيق ، والقيم ، والحسابات ، وما إلى ذلك ، للحقول المتداخلة لتحقيق النتيجة المرجوة.

#### س: هل يؤثر إدخال الحقول المتداخلة على أداء مستند Word باستخدام Aspose.Words for .NET؟

ج: يمكن أن يؤثر إدراج الحقول المتداخلة على أداء مستند Word باستخدام Aspose.Words for .NET ، خاصةً إذا كان المستند يحتوي على عدد كبير من الحقول المتداخلة أو التسلسلات الهرمية المعقدة. يوصى بتحسين الكود وتجنب العمليات غير الضرورية أو المتكررة في الحقول المتداخلة لتحسين الأداء.