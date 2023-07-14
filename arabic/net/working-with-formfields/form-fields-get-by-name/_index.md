---
title: الحصول على حقول النموذج بالاسم
linktitle: الحصول على حقول النموذج بالاسم
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استرداد وتعديل حقول النموذج بالاسم في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-formfields/form-fields-get-by-name/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لاسترداد حقول النماذج بالاسم من مستند Word. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة كائن المستند

 أولاً ، قم بتهيئة ملف`Document` عن طريق توفير المسار إلى المستند المصدر الذي يحتوي على حقول النموذج:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## الخطوة 2: استرجاع حقول النموذج

 بعد ذلك ، قم بالوصول إلى`FormFields`ممتلكات`Range` كائن في المستند لاسترداد جميع حقول النموذج:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

يمكنك استرداد حقول النموذج إما بالفهرس أو بالاسم. في هذا المثال ، نسترجع حقل نموذج باستخدام كلتا الطريقتين:

```csharp
FormField formField1 = documentFormFields[3]; //استرجاع الفهرس
FormField formField2 = documentFormFields["Text2"]; // استرجاع بالاسم
```

## الخطوة 3: تعديل خصائص حقل النموذج

 بمجرد استرداد حقول النموذج ، يمكنك تعديل خصائصها حسب الحاجة. في هذا المثال ، نقوم بتغيير حجم الخط من`formField1` إلى 20 ولون خط`formField2` إلى الأحمر:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## الخطوة 4: حفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

هذا كل شيء! لقد نجحت في استرداد حقول النموذج بالاسم وتعديل خصائصها في مستند Word باستخدام Aspose.Words for .NET.

### مثال على كود المصدر لحقول النموذج الحصول على حسب الاسم باستخدام Aspose.Words for .NET

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

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.

### التعليمات

#### س: كيف يمكنني الحصول على حقل نموذج بالاسم في Aspose.Words؟

 ج: للحصول على حقل نموذج بالاسم في Aspose.Words ، يمكنك استخدام`Document.Range.FormFields[name]` طريقة. تقوم هذه الطريقة بإرجاع حقل النموذج المقابل للاسم المحدد.

#### س: ماذا لو كان حقل النموذج بالاسم المحدد غير موجود في المستند؟

 ج: إذا كان حقل النموذج بالاسم المحدد غير موجود في المستند ، فإن ملف`Document.Range.FormFields[name]` طريقة العودة`null`يمكنك التحقق من هذه النتيجة للتعامل مع الحالات التي لا يتم فيها العثور على حقل النموذج.

#### س: كيف يمكنني تعديل خصائص حقل نموذج موجود؟

ج: بمجرد حصولك على حقل نموذج بالاسم ، يمكنك الوصول إلى خصائصه الفردية لتحريرها. على سبيل المثال ، يمكنك تغيير قيمة الحقل أو تمكين أو تعطيل الرؤية الخاصة به أو تعديل الخصائص الأخرى حسب الحاجة.

#### س: هل يمكنني الحصول على حقول نموذج متعددة بنفس الاسم في مستند؟

 ج: نعم ، من الممكن أن يكون لديك عدة حقول نموذج بنفس الاسم في المستند. في هذه الحالة ، فإن ملف`Document.Range.FormFields[name]` ستعيد الطريقة حقل النموذج الأول الذي تم العثور عليه بالاسم المحدد. إذا كانت لديك حقول نموذج متعددة بنفس الاسم ، فستحتاج إلى أخذ ذلك في الاعتبار عند معالجة الحقول.

#### س: كيف يمكنني تكرار كل حقول النموذج في المستند؟

 ج: للتكرار على جميع حقول النموذج في المستند ، يمكنك استخدام ملف`foreach` حلقة على`Document.Range.FormFields` مجموعة. سيسمح لك ذلك بالوصول إلى كل حقل نموذج على حدة وتنفيذ العمليات على كل منها.