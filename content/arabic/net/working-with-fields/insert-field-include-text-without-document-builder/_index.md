---
title: إدراج حقل يتضمن نصًا بدون أداة إنشاء المستندات
linktitle: قم بإدراج FieldIncludeText بدون منشئ المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقل FieldIncludeText في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-field-include-text-without-document-builder/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم وظيفة "إدراج حقل FieldIncludeText" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

## الخطوة 1: إعداد دليل المستندات

في الكود المقدم، يجب عليك تحديد دليل المستندات الخاصة بك. استبدل القيمة "YOUR DOCUMENT DIRECTORY" بالمسار المناسب لدليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء الوثيقة والفقرة

نبدأ بإنشاء مستند جديد وتهيئة فقرة.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## الخطوة 3: إدراج حقل FieldIncludeText

 نحن نستخدم ال`AppendField()` طريقة لإدراج حقل FieldIncludeText في الفقرة.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

نقوم بعد ذلك بتكوين خصائص حقل FieldIncludeText عن طريق تحديد اسم الإشارة المرجعية واسم الملف المصدر.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

بعد ذلك، نضيف الفقرة إلى نص الوثيقة.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 وأخيراً نسمي`Update()` طريقة تحديث الحقل

```csharp
fieldIncludeText.Update();
```

### مثال على التعليمات البرمجية المصدر لإدراج حقل FieldIncludeText باستخدام Aspose.Words لـ .NET

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء المستند والفقرة.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// أدخل حقل FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

في هذا المثال، قمنا بإنشاء مستند جديد، وقمنا بتهيئة فقرة، وإدراج FieldIncludeTexten لتحديد اسم الإشارة المرجعية واسم الملف المصدر، وحفظنا المستند باسم ملف محدد.

بهذا نختتم دليلنا حول استخدام ميزة "إدراج ملف FieldIncludeText" مع Aspose.Words لـ .NET.

### الأسئلة الشائعة

#### س: كيف يمكنني تحديد الملف المصدر لحقل تضمين النص في Aspose.Words لـ .NET؟

 ج: لتحديد الملف المصدر لحقل تضمين النص في Aspose.Words لـ .NET، يمكنك استخدام`FieldIncludeText.SourceFullName`الخاصية لتعيين المسار الكامل للملف المصدر. تأكد من إمكانية الوصول إلى الملف المصدر وأنه يحتوي على المحتوى الذي تريد تضمينه في حقل تضمين النص.

#### س: هل يمكنني تضمين نص من ماكرو في حقل تضمين النص باستخدام Aspose.Words لـ .NET؟

 ج: نعم، يمكنك تضمين نص من ماكرو في حقل تضمين النص باستخدام Aspose.Words لـ .NET. يمكنك استخدام ال`FieldIncludeText.IncludeText` الخاصية لتحديد اسم الماكرو الذي يجب تضمين محتواه في الحقل.

#### س: هل يؤثر إدراج حقل تضمين نص بدون أداة إنشاء المستندات على بنية مستند Word مع Aspose.Words for .NET؟

ج: إن إدراج حقل تضمين نص بدون أداة إنشاء المستندات لا يؤثر بشكل مباشر على بنية مستند Word. ومع ذلك، فإنه يضيف عنصر حقل جديد إلى محتوى المستند. يمكنك التعامل مع بنية المستند عن طريق إضافة العناصر الموجودة أو حذفها أو تعديلها وفقًا لاحتياجاتك.

#### س: هل يمكنني تخصيص مظهر حقل تضمين النص في مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لا يقوم حقل تضمين النص بتخصيص مظهره مباشرة في مستند Word. ومع ذلك، يمكنك تنسيق النص المضمن باستخدام خصائص الفقرة، وخصائص الخط، وكائنات التنسيق الأخرى المتوفرة في Aspose.Words for .NET.