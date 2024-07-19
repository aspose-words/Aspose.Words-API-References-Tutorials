---
title: إدراج حقول النموذج
linktitle: إدراج حقول النموذج
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج حقول النموذج المنسدلة في مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-formfields/insert-form-fields/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك حول كيفية إدراج حقول النموذج، وتحديدًا حقل النموذج المنسدل، في مستند Word باستخدام Aspose.Words for .NET. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء، تأكد من تثبيت Aspose.Words for .NET وإعداده في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك، قم بتنزيل المكتبة وتثبيتها من[Aspose.Releases]https://releases.aspose.com/words/net/.

## الخطوة 1: تهيئة المستند وكائنات DocumentBuilder

 أولاً، قم بتهيئة`Document`و`DocumentBuilder` أشياء:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج حقل نموذج منسدل

 بعد ذلك، حدد الخيارات لحقل النموذج المنسدل وأدخله في المستند باستخدام الملف`InsertComboBox` طريقة`DocumentBuilder` هدف. في هذا المثال، نقوم بإدراج حقل نموذج منسدل يسمى "DropDown" مع ثلاثة خيارات: "واحد"، و"اثنان"، و"ثلاثة":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## الخطوة 3: حفظ المستند

أخيرًا، احفظ المستند:

```csharp
doc.Save("OutputDocument.docx");
```

هذا كل شيء! لقد نجحت في إدراج حقل نموذج منسدل في مستند Word باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لإدراج حقول النموذج باستخدام Aspose.Words لـ .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك المحددة.

### الأسئلة الشائعة

#### س: كيف يمكنني إدراج حقل نموذج لنوع النص في Aspose.Words؟

 ج: لإدراج حقل نموذج نوع النص في Aspose.Words، يمكنك استخدام`FormField` الصف وتعيينه`Type`الملكية ل`FormFieldType.Text`. يمكنك أيضًا تخصيص خصائص أخرى مثل الاسم والتسمية والخيارات.

#### س: هل من الممكن إنشاء حقل نموذج من نوع خانة الاختيار في المستند؟

 ج: نعم، من الممكن إنشاء حقل نموذج من نوع خانة الاختيار في مستند Aspose.Words. يمكنك استخدام ال`FormField` الصف وتعيينه`Type`الملكية ل`FormFieldType.CheckBox` لإنشاء خانة الاختيار. يمكنك بعد ذلك تخصيص خصائص مربع الاختيار حسب الحاجة.

#### س: كيف يمكنني إضافة حقل نموذج من القائمة المنسدلة إلى المستند؟

 ج: لإضافة حقل نموذج من النوع المنسدل في مستند Aspose.Words، استخدم الملف`FormField` الصف وتعيينه`Type`الملكية ل`FormFieldType.DropDown` . يمكنك بعد ذلك ضبط خيارات القائمة المنسدلة باستخدام`DropDownItems` ملكية.

#### س: هل يمكنني تعيين قيمة افتراضية لحقل نموذج في Aspose.Words؟

ج: نعم، يمكنك تعيين قيمة افتراضية لحقل نموذج في Aspose.Words. استخدم ال`FormField.Result` الخاصية لتحديد القيمة الأولية لحقل النموذج.

#### س: كيف يمكنني استرداد البيانات المدخلة في حقول النموذج في Aspose.Words؟

 ج: لاسترداد البيانات المدخلة في حقول النموذج في Aspose.Words، يمكنك استخدام`FormField.Result` الخاصية التي تحتوي على القيمة التي أدخلها المستخدم. يمكنك الوصول إلى هذه الخاصية لكل حقل نموذج في مستندك.