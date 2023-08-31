---
title: أدخل حقل الدمج باستخدام DOM
linktitle: أدخل حقل الدمج باستخدام DOM
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقول دمج الحقول المخصصة في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-merge-field-using-dom/
---

فيما يلي دليل خطوة بخطوة لشرح كود مصدر C# أدناه والذي يستخدم ميزة "إدراج حقل دمج الحقول" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: نقل المؤشر إلى الفقرة

 نحن نستخدم ال`MoveTo()` طريقة DocumentBuilder لتحريك المؤشر إلى الفقرة التي نريد إدراج حقل دمج الحقول فيها.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## الخطوة 4: إدراج حقل دمج الحقول

 نحن نستخدم DocumentBuilder`InsertField()` طريقة لإدراج حقل دمج الحقول في الفقرة.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

نقوم بعد ذلك بتكوين خصائص حقل دمج الحقول عن طريق تحديد الخيارات المناسبة، مثل اسم الحقل، والنص الموجود قبل الحقل وبعده، وخيارات التنسيق الرأسي.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 وأخيراً نسمي`Update()` طريقة تحديث الحقل

```csharp
field. Update();
```

### نموذج التعليمات البرمجية المصدر لإدراج حقل دمج الحقول مع Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند وDocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// نقل المؤشر إلى الفقرة.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// أدخل حقل دمج الحقول.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// قم بتحديث الحقل.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

في هذا المثال، قمنا بإنشاء مستند جديد، ونقلنا المؤشر إلى الفقرة المطلوبة، ثم قمنا بإدراج حقل دمج الحقول في المستند.

### الأسئلة الشائعة

#### س: كيف يمكنني إدراج حقل دمج في مستند Word باستخدام Aspose.Words لـ .NET مع DOM؟

ج: لإدراج حقل دمج في مستند Word باستخدام Aspose.Words لـ .NET مع DOM، يمكنك اتباع الخطوات التالية:

1. انتقل إلى الفقرة التي تريد إدراج حقل الدمج فيها.
2.  إنشاء`FieldMergeField` هدف.
3. قم بتعيين خصائص حقل الدمج، مثل اسم الحقل وخيارات التنسيق.
4.  أضف حقل الدمج إلى الفقرة باستخدام`Paragraph.AppendChild` طريقة.

#### س: كيف يمكنني تحديد البيانات المصدر لحقل الدمج في Aspose.Words لـ .NET؟

ج: لتحديد البيانات المصدر لحقل الدمج في Aspose.Words لـ .NET، يمكنك استخدام`FieldMergeField.FieldName` طريقة لتعيين اسم حقل الدمج، وهو اسم حقل في مصدر بيانات خارجي مثل ملف CSV، أو قاعدة البيانات، وما إلى ذلك. يمكنك أيضًا استخدام`FieldMergeField.Text` طريقة لتعيين قيمة حقل الدمج مباشرة.

#### س: هل يمكنني تخصيص مظهر حقل الدمج في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: نعم، يمكنك تخصيص مظهر حقل الدمج في مستند Word باستخدام Aspose.Words لـ .NET. يمكنك ضبط خيارات التنسيق مثل الحالة والخط واللون وما إلى ذلك باستخدام خصائص الملف`FieldMergeField` هدف.

#### س: كيف يمكنني التحقق مما إذا كان قد تم إدراج حقل دمج بنجاح في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للتحقق من إدراج حقل الدمج بنجاح، يمكنك استعراض محتوى المستند والبحث عن مثيلات حقل الدمج. يمكنك استخدام أساليب وخصائص`Document` كائن للوصول إلى الفقرات والحقول والعناصر الأخرى في المستند.

#### س: هل يؤثر إدراج حقل دمج باستخدام DOM على بنية مستند Word مع Aspose.Words لـ .NET؟

ج: لا يؤثر إدراج حقل دمج باستخدام DOM بشكل مباشر على بنية مستند Word. ومع ذلك، فإنه يضيف عنصر حقل جديد إلى محتوى المستند. يمكنك التعامل مع بنية المستند عن طريق إضافة العناصر الموجودة أو حذفها أو تعديلها وفقًا لاحتياجاتك.