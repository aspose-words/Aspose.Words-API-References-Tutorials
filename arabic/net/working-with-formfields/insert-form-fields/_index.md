---
title: أدخل حقول النموذج
linktitle: أدخل حقول النموذج
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج حقول نموذج القائمة المنسدلة في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-formfields/insert-form-fields/
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

 بعد ذلك ، حدد خيارات حقل نموذج القائمة المنسدلة وأدخله في المستند باستخدام ملف`InsertComboBox` طريقة`DocumentBuilder` هدف. في هذا المثال ، نقوم بإدراج حقل نموذج منسدلة باسم "DropDown" مع ثلاثة خيارات: "واحد" و "اثنان" و "ثلاثة":

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

### التعليمات

#### س: كيف يمكنني إدخال حقل نموذج نوع النص في Aspose.Words؟

 ج: لإدراج حقل نموذج نوع النص في Aspose.Words ، يمكنك استخدام`FormField` فئة وضبطها`Type` ملكية ل`FormFieldType.Text`. يمكنك أيضًا تخصيص خصائص أخرى مثل الاسم والتسمية والخيارات.

#### س: هل من الممكن إنشاء حقل نموذج نوع خانة الاختيار في وثيقة؟

 ج: نعم ، من الممكن إنشاء حقل نموذج نوع مربع الاختيار في وثيقة Aspose.Words. يمكنك استخدام ال`FormField` فئة وضبطها`Type` ملكية ل`FormFieldType.CheckBox` لإنشاء مربع اختيار. يمكنك بعد ذلك تخصيص خصائص مربع الاختيار حسب الحاجة.

#### س: كيف يمكنني إضافة حقل نموذج نوع القائمة المنسدلة إلى مستند؟

 ج: لإضافة حقل نموذج من القائمة المنسدلة في مستند Aspose.Words ، استخدم`FormField` فئة وضبطها`Type` ملكية ل`FormFieldType.DropDown` . يمكنك بعد ذلك تعيين خيارات القائمة المنسدلة باستخدام ملف`DropDownItems` ملكية.

#### س: هل يمكنني تعيين قيمة افتراضية لحقل نموذج في Aspose.Words؟

ج: نعم ، يمكنك تعيين قيمة افتراضية لحقل نموذج في Aspose.Words. استخدم ال`FormField.Result` خاصية لتحديد القيمة الأولية لحقل النموذج.

#### س: كيف يمكنني استرجاع البيانات المدخلة في حقول النموذج في Aspose.Words؟

 ج: لاسترداد البيانات التي تم إدخالها في حقول النموذج في Aspose.Words ، يمكنك استخدام`FormField.Result` الخاصية التي تحتوي على القيمة التي أدخلها المستخدم. يمكنك الوصول إلى هذه الخاصية لكل حقل نموذج في المستند الخاص بك.