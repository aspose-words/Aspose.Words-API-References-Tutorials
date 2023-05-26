---
title: أدخل حقل كتلة عنوان دمج المراسلات باستخدام DOM
linktitle: أدخل حقل كتلة عنوان دمج المراسلات باستخدام DOM
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقل كتلة عنوان دمج المراسلات في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
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
