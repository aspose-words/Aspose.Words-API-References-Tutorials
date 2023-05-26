---
title: أدخل حقول النموذج
linktitle: أدخل حقول النموذج
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إدراج حقول نموذج القائمة المنسدلة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/working-with-formfields/insert-form-fields/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية إدراج حقول النموذج ، وتحديداً حقل نموذج القائمة المنسدلة ، في مستند Word باستخدام Aspose.Words for .NET. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة المستند وكائنات DocumentBuilder

 أولاً ، قم بتهيئة ملف`Document` و`DocumentBuilder` أشياء:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج حقل نموذج منسدل

 بعد ذلك ، حدد خيارات حقل نموذج القائمة المنسدلة وأدخله في المستند باستخدام ملف`InsertComboBox` طريقة`DocumentBuilder`هدف. في هذا المثال ، نقوم بإدراج حقل نموذج منسدلة باسم "DropDown" مع ثلاثة خيارات: "واحد" و "اثنان" و "ثلاثة":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## الخطوة 3: حفظ المستند

أخيرًا ، احفظ المستند:

```csharp
doc.Save("OutputDocument.docx");
```

هذا كل شيء! لقد نجحت في إدراج حقل نموذج منسدل في مستند Word باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لإدراج حقول النموذج باستخدام Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.