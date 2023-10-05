---
title: الحصول على حقول النموذج بالاسم
linktitle: الحصول على حقول النموذج بالاسم
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استرداد حقول النموذج وتعديلها حسب الاسم في مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-formfields/form-fields-get-by-name/
---

في هذا البرنامج التعليمي خطوة بخطوة، سنرشدك حول كيفية استخدام Aspose.Words لـ .NET لاسترداد حقول النموذج بالاسم من مستند Word. سنشرح لك كود مصدر C# المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

 للبدء، تأكد من تثبيت Aspose.Words for .NET وإعداده في بيئة التطوير لديك. إذا لم تكن قد قمت بذلك، قم بتنزيل المكتبة وتثبيتها من[Aspose.Releases]https://releases.aspose.com/words/net/.

## الخطوة 1: تهيئة كائن المستند

 أولاً، قم بتهيئة`Document` الكائن من خلال توفير المسار إلى المستند المصدر الذي يحتوي على حقول النموذج:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## الخطوة 2: استرداد حقول النموذج

 بعد ذلك، قم بالوصول إلى`FormFields` ملكية`Range` كائن في المستند لاسترداد كافة حقول النموذج:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

يمكنك استرداد حقول النموذج إما عن طريق الفهرس أو بالاسم. في هذا المثال، نقوم باسترداد حقل نموذج باستخدام كلا الطريقتين:

```csharp
FormField formField1 = documentFormFields[3]; // الاسترجاع عن طريق الفهرس
FormField formField2 = documentFormFields["Text2"]; // الاسترجاع بالاسم
```

## الخطوة 3: تعديل خصائص حقل النموذج

بمجرد استرجاع حقول النموذج، يمكنك تعديل خصائصها حسب الحاجة. في هذا المثال، قمنا بتغيير حجم الخط`formField1` إلى 20 ولون الخط`formField2` إلى الأحمر:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## الخطوة 4: حفظ المستند

وأخيرا، احفظ الوثيقة المعدلة:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

هذا كل شيء! لقد نجحت في استرداد حقول النموذج حسب الاسم وتعديل خصائصها في مستند Word باستخدام Aspose.Words for .NET.

### مثال على التعليمات البرمجية المصدر لحقول النموذج التي يتم الحصول عليها بالاسم باستخدام Aspose.Words لـ .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك المحددة.

### الأسئلة الشائعة

#### س: كيف يمكنني الحصول على حقل نموذج بالاسم في Aspose.Words؟

 ج: للحصول على حقل نموذج بالاسم في Aspose.Words، يمكنك استخدام`Document.Range.FormFields[name]` طريقة. تقوم هذه الطريقة بإرجاع حقل النموذج المطابق للاسم المحدد.

#### س: ماذا لو كان حقل النموذج بالاسم المحدد غير موجود في المستند؟

 ج: إذا كان حقل النموذج بالاسم المحدد غير موجود في المستند، فسيتم`Document.Range.FormFields[name]` سوف تعود الطريقة`null`. يمكنك التحقق من هذه النتيجة للتعامل مع الحالات التي لم يتم العثور فيها على حقل النموذج.

#### س: كيف يمكنني تعديل خصائص حقل النموذج الذي تم العثور عليه؟

ج: بمجرد حصولك على حقل نموذج بالاسم، يمكنك الوصول إلى خصائصه الفردية لتحريرها. على سبيل المثال، يمكنك تغيير قيمة الحقل، أو تمكين رؤيته أو تعطيلها، أو تعديل الخصائص الأخرى حسب الحاجة.

#### س: هل يمكنني الحصول على حقول نماذج متعددة بنفس الاسم في المستند؟

 ج: نعم، من الممكن وجود حقول نماذج متعددة بنفس الاسم في المستند. في هذه الحالة،`Document.Range.FormFields[name]` ستعيد الطريقة حقل النموذج الأول الذي تم العثور عليه بالاسم المحدد. إذا كان لديك حقول نموذج متعددة بنفس الاسم، فسوف تحتاج إلى أخذ ذلك في الاعتبار عند التعامل مع الحقول.

#### س: كيف يمكنني التكرار على كافة حقول النموذج في المستند؟

 ج: للتكرار على كافة حقول النموذج في المستند، يمكنك استخدام ملف`foreach` حلقة على`Document.Range.FormFields` مجموعة. سيسمح لك هذا بالوصول إلى كل حقل نموذج على حدة وتنفيذ العمليات على كل واحد منهم.