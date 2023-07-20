---
title: أدخل ASKField بدون Document Builder
linktitle: أدخل ASKField بدون Document Builder
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج حقل ASK في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-askfield-with-out-document-builder/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج حقل ASK بدون DocumentBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: إدخال حقل ASK

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل ASK في الفقرة.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

ثم نقوم بتكوين الخصائص المختلفة لحقل ASK عن طريق تحديد القيم المطلوبة.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### مثال على الكود المصدري لإدخال حقل ASK بدون DocumentBuilder مع Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// أدخل حقل ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

في هذا المثال ، أنشأنا مستندًا جديدًا ، وأدخلنا حقل ASK دون استخدام DocumentBuilder ، وقمنا بتكوين الخصائص المختلفة للحقل ، وحفظنا المستند باسم ملف محدد.

هذا يختتم دليلنا حول استخدام ميزة "إدراج حقل ASK بدون DocumentBuilder" مع Aspose.Words for .NET.

### التعليمات

#### س: ما هو حقل ASK في Aspose.Words؟

ج: يتم استخدام حقل ASK في Aspose.Words لطرح سؤال على المستخدم عند فتح مستند. غالبًا ما يتم استخدامه لطلب معلومات أو ملاحظات محددة قد تختلف من مستخدم لآخر.

#### س: كيفية إدراج حقل ASK في مستند Word دون استخدام Document Builder في Aspose.Words؟

ج: لإدراج حقل ASK في مستند Word دون استخدام Document Builder في Aspose.Words ، يمكنك اتباع الخطوات التالية:

1. استيراد فئة المستند والحقل من Aspose.Words.Fields namespace.
2. قم بإنشاء مثيل من المستند عن طريق تحميل المستند الحالي.
3. استخدم أسلوب InsertField لإدراج حقل ASK عن طريق تحديد اسم السؤال.
4. احفظ المستند.

#### س: كيف أحصل على استجابة المستخدم لحقل ASK في مستند Word؟

ج: للحصول على استجابة المستخدم لحقل ASK في مستند Word ، يمكنك استخدام طريقة GetFieldNames المتوفرة في فئة المستند. تقوم هذه الطريقة بإرجاع قائمة بأسماء الحقول الموجودة في المستند. يمكنك بعد ذلك التحقق مما إذا كان اسم الحقل ASK موجودًا في القائمة واسترداد الاستجابة المرتبطة.

#### س: هل يمكن استخدام حقل ASK لطلب مزيد من المعلومات من المستخدم؟

ج: نعم ، يمكن استخدام حقل ASK لطلب أجزاء متعددة من المعلومات من المستخدم. يمكنك إدراج عدة حقول ASK في المستند ، ولكل منها سؤال مختلف. عند فتح المستند ، ستتم مطالبة المستخدم بالإجابات المقابلة.