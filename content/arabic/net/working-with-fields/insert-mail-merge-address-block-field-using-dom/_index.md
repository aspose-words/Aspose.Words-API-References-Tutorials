---
title: أدخل حقل كتلة عنوان دمج المراسلات باستخدام DOM
linktitle: أدخل حقل كتلة عنوان دمج المراسلات باستخدام DOM
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج حقل كتلة عنوان دمج المراسلات في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

فيما يلي دليل تفصيلي خطوة بخطوة لشرح الكود المصدري C # أدناه ، والذي يستخدم ميزة "إدراج حقل كتلة عنوان دمج المراسلات" في Aspose.Words for .NET. تأكد من اتباع كل خطوة بعناية للحصول على النتائج المرجوة.

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

## الخطوة 3: تحريك المؤشر إلى الفقرة

 نحن نستخدم برنامج DocumentBuilder`MoveTo()` طريقة لتحريك المؤشر إلى الفقرة حيث نريد إدراج حقل كتلة عنوان دمج المراسلات.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## الخطوة 4: إدراج حقل كتلة عنوان دمج المراسلات

 نحن نستخدم برنامج DocumentBuilder`InsertField()` طريقة لإدراج حقل كتلة عنوان دمج المراسلات في الفقرة.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

نقوم بعد ذلك بتكوين خصائص حقل كتلة العنوان لتحديد الخيارات المناسبة ، مثل تضمين اسم البلد / المنطقة ، وتنسيق العنوان وفقًا للبلد / المنطقة ، وأسماء البلد / المنطقة المستبعدة ، وتنسيق الاسم والعنوان ، ومعرف اللغة.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 أخيرًا ، نسمي`Update()` طريقة لتحديث المجال.

```csharp
field. Update();
```

### نموذج لشفرة المصدر لإدخال حقل كتلة عنوان دمج المراسلات مع Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// نريد إدراج كتلة عنوان لدمج البريد مثل هذا:
// {ADDRESSBLOCK \\ c 1 \\ d \\ e Test2 \\ f Test3 \\ l \ "Test 4 \"}

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// {ADDRESSBLOCK \\ c 1 "}
field.IncludeCountryOrRegionName = "1";

// {ADDRESSBLOCK \\ c 1 \\ d "}
field.FormatAddressOnCountryOrRegion = true;

// {ADDRESSBLOCK \\ c 1 \\ d \\ e Test2}
field.ExcludedCountryOrRegionName = "Test2";

// {ADDRESSBLOCK \\ c 1 \\ d \\ e Test2 \\ f Test3}
field.NameAndAddressFormat = "Test3";

// {ADDRESSBLOCK \\ c 1 \\ d \\ e Test2 \\ f Test3 \\ l \ "Test 4 \"}
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### التعليمات

#### س: كيف يمكنني تخصيص تنسيق العنوان البريدي في مستند Word باستخدام Aspose.Words for .NET؟

 ج: يمكنك تخصيص تنسيق العنوان البريدي في مستند Word باستخدام Aspose.Words for .NET باستخدام خصائص`FieldAddressBlock`هدف. يمكنك تعيين خيارات التنسيق مثل نمط العنوان والفواصل والعناصر الاختيارية وما إلى ذلك للحصول على التنسيق المطلوب.

#### س: كيف يمكنني تحديد البيانات المصدر لحقل العنوان البريدي في Aspose.Words for .NET؟

 ج: لتحديد مصدر البيانات لحقل العنوان البريدي في Aspose.Words for .NET ، يمكنك استخدام`FieldAddressBlock.StartAddress` و`FieldAddressBlock.EndAddress` ملكيات. تُستخدم هذه الخصائص لتحديد نطاقات العناوين في مصدر البيانات الخارجي ، مثل ملف CSV وقاعدة البيانات وما إلى ذلك.

#### س: هل يمكنني تضمين عناصر اختيارية في حقل العنوان البريدي مع Aspose.Words for .NET؟

 ج: نعم ، يمكنك تضمين عناصر اختيارية في حقل العنوان البريدي مع Aspose.Words for .NET. يمكنك تحديد العناصر الاختيارية باستخدام ملف`FieldAddressBlock.OmitOptional` طريقة لتحديد ما إذا كان سيتم تضمين أو استبعاد عناصر اختيارية مثل اسم المستلم واسم الشركة وما إلى ذلك.

#### س: هل إدخال حقل عنوان بريدي باستخدام DOM يؤثر على بنية مستند Word مع Aspose.Words for .NET؟

ج: لا يؤثر إدخال حقل عنوان بريدي باستخدام DOM بشكل مباشر على بنية مستند Word. ومع ذلك ، فإنه يضيف عنصر حقل جديدًا إلى محتوى المستند. يمكنك معالجة هيكل المستند عن طريق إضافة أو حذف أو تعديل العناصر الموجودة وفقًا لاحتياجاتك.