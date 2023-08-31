---
title: أدخل حقل المؤلف
linktitle: أدخل حقل المؤلف
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقل المؤلف في مستندات Word الخاصة بك باستخدام Aspose.Words لـ .NET. حدد اسم المؤلف لتخصيص مستنداتك.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-author-field/
---


فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة "إدراج حقل AUTHOR" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: أدخل حقل المؤلف

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل AUTHOR في الفقرة.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 ثم نقوم بتكوين الحقل`AuthorName` الخاصية لتحديد اسم المؤلف.

```csharp
field. AuthorName = "Test1";
```

 وأخيراً نسمي`Update()` طريقة تحديث الحقل

```csharp
field. Update();
```

### مثال على الكود المصدري لإدراج حقل AUTHOR باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// إنشاء الوثيقة.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// أدخل حقل المؤلف.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

في هذا المثال، قمنا بإنشاء مستند جديد، وأدخلنا حقل المؤلف، وقمنا بتكوين اسم المؤلف، وحفظنا المستند باسم ملف محدد.

بهذا نختتم دليلنا حول استخدام ميزة "إدراج حقل المؤلف" مع Aspose.Words for .NET.

### الأسئلة الشائعة

#### س: ما هو حقل المؤلف في Aspose.Words؟

ج: حقل المؤلف في Aspose.Words هو حقل خاص يقوم تلقائيًا بإدراج اسم المؤلف وتحديثه في مستند Word. يتم استخدامه غالبًا للإشارة إلى من قام بإنشاء المستند أو تعديله.

#### س: كيفية تحديث حقل المؤلف في مستند Word باستخدام Aspose.Words؟

ج: يمكن تحديث حقل المؤلف في مستند Word ليعكس اسم المؤلف الحالي. للقيام بذلك، يمكنك استخدام طريقة UpdateFields المتوفرة في فئة المستند. ستقوم هذه الطريقة بتحديث كافة الحقول في المستند، بما في ذلك حقل المؤلف.

#### س: هل من الممكن تخصيص تنسيق حقل المؤلف في مستند Word؟

ج: نعم، من الممكن تخصيص تنسيق حقل المؤلف في مستند Word. افتراضيًا، يعرض حقل المؤلف اسم المؤلف ببساطة. ومع ذلك، يمكنك إضافة معلومات إضافية مثل تاريخ ووقت التعديل باستخدام خيارات التنسيق المتوفرة في Aspose.Words.

#### س: هل حقل المؤلف حساس للتغييرات اللاحقة لاسم المؤلف؟

ج: نعم، حقل المؤلف حساس للتغييرات اللاحقة لاسم المؤلف. إذا قمت بتغيير اسم المؤلف في خصائص المستند، فسيتم تحديث حقل المؤلف تلقائيًا بالاسم الجديد عند تحديث حقول المستند.