---
title: قم بإدراج حقل كتلة عنوان دمج البريد باستخدام DOM
linktitle: قم بإدراج حقل كتلة عنوان دمج البريد باستخدام DOM
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقل كتلة عنوان دمج البريد في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

فيما يلي دليل خطوة بخطوة لشرح التعليمات البرمجية المصدر لـ C# أدناه، والتي تستخدم ميزة "إدراج حقل كتلة عنوان دمج البريد" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

 نحن نستخدم DocumentBuilder`MoveTo()` طريقة لتحريك المؤشر إلى الفقرة التي نريد إدراج حقل كتلة عنوان دمج المراسلات فيها.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## الخطوة 4: إدراج حقل كتلة عنوان دمج المراسلات

 نحن نستخدم DocumentBuilder`InsertField()` طريقة لإدراج حقل كتلة عنوان دمج المراسلات في الفقرة.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

نقوم بعد ذلك بتكوين خصائص حقل كتلة العنوان مع تحديد الخيارات المناسبة، مثل تضمين اسم البلد/المنطقة، وتنسيق العنوان وفقًا للبلد/المنطقة، واستبعاد أسماء البلدان/المناطق، وتنسيق الاسم والعنوان، ومعرف اللغة.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 وأخيراً نسمي`Update()` طريقة تحديث الحقل

```csharp
field. Update();
```

### نموذج التعليمات البرمجية المصدر لإدراج حقل كتلة عنوان دمج المراسلات باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// نريد إدراج كتلة عنوان دمج البريد مثل هذا:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"اختبار 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { كتلة العنوان \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { كتلة العنوان \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { كتلة العنوان \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { كتلة العنوان \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"اختبار 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### الأسئلة الشائعة

#### س: كيف يمكنني تخصيص تنسيق العنوان البريدي في مستند Word باستخدام Aspose.Words لـ .NET؟

 ج: يمكنك تخصيص تنسيق العنوان البريدي في مستند Word باستخدام Aspose.Words لـ .NET باستخدام خصائص`FieldAddressBlock`هدف. يمكنك ضبط خيارات التنسيق مثل نمط العنوان والفواصل والعناصر الاختيارية وما إلى ذلك للحصول على التنسيق المطلوب.

#### س: كيف يمكنني تحديد البيانات المصدر لحقل العنوان البريدي في Aspose.Words for .NET؟

 ج: لتحديد البيانات المصدر لحقل العنوان البريدي في Aspose.Words لـ .NET، يمكنك استخدام`FieldAddressBlock.StartAddress`و`FieldAddressBlock.EndAddress` ملكيات. تُستخدم هذه الخصائص لتحديد نطاقات العناوين في مصدر البيانات الخارجي، مثل ملف CSV وقاعدة البيانات وما إلى ذلك.

#### س: هل يمكنني تضمين عناصر اختيارية في حقل العنوان البريدي باستخدام Aspose.Words for .NET؟

 ج: نعم، يمكنك تضمين عناصر اختيارية في حقل العنوان البريدي باستخدام Aspose.Words for .NET. يمكنك تحديد العناصر الاختيارية باستخدام`FieldAddressBlock.OmitOptional` طريقة لتحديد ما إذا كان سيتم تضمين أو استبعاد العناصر الاختيارية مثل اسم المستلم واسم الشركة وما إلى ذلك.

#### س: هل يؤثر إدراج حقل عنوان بريدي باستخدام DOM على بنية مستند Word مع Aspose.Words for .NET؟

ج: إن إدراج حقل عنوان بريدي باستخدام DOM لا يؤثر بشكل مباشر على بنية مستند Word. ومع ذلك، فإنه يضيف عنصر حقل جديد إلى محتوى المستند. يمكنك التعامل مع بنية المستند عن طريق إضافة العناصر الموجودة أو حذفها أو تعديلها وفقًا لاحتياجاتك.