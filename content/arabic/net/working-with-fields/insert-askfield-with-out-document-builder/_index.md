---
title: أدخل ASKField بدون منشئ المستندات
linktitle: أدخل ASKField بدون منشئ المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقل ASK في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-askfield-with-out-document-builder/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة "إدراج حقل ASK بدون DocumentBuilder" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: إدراج حقل ASK

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل ASK في الفقرة.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

نقوم بعد ذلك بتكوين الخصائص المختلفة لحقل ASK من خلال تحديد القيم المطلوبة.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 وأخيراً نسمي`Update()` طريقة تحديث الحقل

```csharp
field. Update();
```

### مثال على التعليمات البرمجية المصدر لإدراج حقل ASK بدون DocumentBuilder مع Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// أدخل الحقل "السؤال".
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

في هذا المثال، قمنا بإنشاء مستند جديد، وإدراج حقل ASK دون استخدام DocumentBuilder، وقمنا بتكوين الخصائص المتنوعة للحقل، وحفظنا المستند باسم ملف محدد.

بهذا نختتم دليلنا حول استخدام ميزة "إدراج حقل ASK بدون DocumentBuilder" مع Aspose.Words لـ .NET.

### الأسئلة الشائعة

#### س: ما هو حقل ASK في Aspose.Words؟

ج: يتم استخدام حقل ASK في Aspose.Words لطرح سؤال على المستخدم عند فتح مستند. غالبًا ما يتم استخدامه لطلب معلومات أو تعليقات محددة قد تختلف من مستخدم لآخر.

#### س: كيفية إدراج حقل ASK في مستند Word دون استخدام Document Builder في Aspose.Words؟

ج: لإدراج حقل ASK في مستند Word دون استخدام Document Builder في Aspose.Words، يمكنك اتباع الخطوات التالية:

1. قم باستيراد فئة المستند والحقل من مساحة الاسم Aspose.Words.Fields.
2. قم بإنشاء مثيل للمستند عن طريق تحميل المستند الموجود لديك.
3. استخدم الأسلوب InsertField لإدراج حقل ASK عن طريق تحديد اسم السؤال.
4. احفظ المستند.

#### س: كيف يمكنني الحصول على استجابة المستخدم لحقل ASK في مستند Word؟

ج: للحصول على استجابة المستخدم لحقل ASK في مستند Word، يمكنك استخدام أسلوب GetFieldNames المتوفر في فئة المستند. تقوم هذه الطريقة بإرجاع قائمة بأسماء الحقول الموجودة في المستند. يمكنك بعد ذلك التحقق من وجود اسم حقل ASK في القائمة واسترداد الاستجابة المرتبطة به.

#### س: هل يمكن استخدام الحقل ASK لطلب المزيد من المعلومات من المستخدم؟

ج: نعم، يمكن استخدام حقل "السؤال" لطلب أجزاء متعددة من المعلومات من المستخدم. يمكنك إدراج عدة حقول ASK في مستندك، كل منها يحتوي على سؤال مختلف. عند فتح المستند، سيُطلب من المستخدم الإجابات المقابلة.