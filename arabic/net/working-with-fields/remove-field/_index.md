---
title: إزالة الحقل
linktitle: إزالة الحقل
second_title: Aspose.Words لمراجع .NET API
description: في هذا الدليل ، ستتعلم كيفية حذف حقل معين في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/remove-field/
---
فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم وظيفة "إزالة الحقل" في Aspose.Words for .NET. اتبع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستند

في الكود المقدم ، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب إلى دليل المستندات.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة الثانية: تحميل المستند

نبدأ بتحميل المستند الحالي من الملف المحدد.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## الخطوة 3: حذف الحقل

 نختار الحقل الأول في نطاق المستندات ونستخدم ملف`Remove()` طريقة إزالته.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## الخطوة 4: حفظ المستند

 أخيرًا ، نسمي`Save()` طريقة لحفظ المستند المعدل.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### مثال على شفرة المصدر لحذف الحقل باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند.
Document doc = new Document(dataDir + "Various fields.docx");

// اختيار الحقل المراد حذفه.
Field field = doc.Range.Fields[0];
field. Remove();

// احفظ المستند.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

اتبع هذه الخطوات لحذف حقل معين في وثيقتك باستخدام Aspose.Words for .NET.

### التعليمات

#### س: كيف يمكنني حذف حقل في مستند Word باستخدام Aspose.Words for .NET؟

 ج: لإزالة حقل في مستند Word باستخدام Aspose.Words for .NET ، يمكنك تكرار الحقول في المستند باستخدام`FieldStart` فئة واستخدام`FieldStart.Remove`طريقة لإزالة الحقل.

#### س: هل من الممكن حذف حقول معينة فقط في مستند Word باستخدام Aspose.Words for .NET؟

 ج: نعم ، من الممكن حذف حقول معينة فقط في مستند Word باستخدام Aspose.Words for .NET. يمكنك تصفية الحقول المراد حذفها باستخدام معايير محددة ، مثل اسم الحقل أو الخصائص الأخرى ذات الصلة. ثم يمكنك إزالة الحقول المقابلة باستخدام`FieldStart.Remove` طريقة.

#### س: كيف يمكنني التحقق مما إذا تم حذف حقل بنجاح في مستند Word باستخدام Aspose.Words for .NET؟

 ج: للتحقق مما إذا تمت إزالة أحد الحقول بنجاح في مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام`Document.Range.Fields.Contains` طريقة للتحقق مما إذا كان الحقل لا يزال موجودًا في المستند بعد حذفه.

#### س: ما هي النتائج المترتبة على حذف حقل في مستند Word باستخدام Aspose.Words for .NET؟

ج: عند حذف حقل في مستند Word باستخدام Aspose.Words for .NET ، يتم أيضًا حذف جميع البيانات المرتبطة بهذا الحقل. قد يؤثر ذلك على محتوى المستند وتنسيقه ، خاصةً إذا تم استخدام الحقل لعرض المعلومات الديناميكية.

#### س: هل من الممكن استعادة حقل محذوف في مستند Word باستخدام Aspose.Words for .NET؟

ج: لسوء الحظ ، بمجرد حذف حقل من مستند Word مع Aspose.Words for .NET ، لا يمكن استعادته تلقائيًا. يوصى بحفظ المستند الخاص بك قبل حذف الحقول ، في حالة احتياجك لاستعادتها لاحقًا.