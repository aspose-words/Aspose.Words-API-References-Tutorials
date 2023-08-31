---
title: تغيير مصدر ثقافة تحديث الحقل
linktitle: تغيير مصدر ثقافة تحديث الحقل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تغيير مصدر ثقافة التحديث الميداني، دليل خطوة بخطوة لتعديل مصدر الثقافة في Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/change-field-update-culture-source/
---

في هذا البرنامج التعليمي، سنرشدك خلال عملية تغيير مصدر ثقافة التحديث الميداني في مستندات Word باستخدام Aspose.Words for .NET. من خلال تعديل مصدر البيانات الموروثة، يمكنك التحكم في تنسيق التاريخ أثناء عمليات التحديث الميداني ودمج المراسلات. سنزودك بكود مصدر C# الضروري والتعليمات خطوة بخطوة لتحقيق ذلك.

## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
- Aspose.Words لمكتبة .NET المثبتة على نظامك.

## الخطوة 1: إنشاء مستند و DocumentBuilder
للبدء، قم بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: إدراج محتوى باستخدام لغة محددة
بعد ذلك، قم بتعيين اللغة إلى الألمانية وأدخل الحقول بتنسيق التاريخ:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

في الكود أعلاه، قمنا بتعيين لغة الخط إلى الألمانية (معرف اللغة 1031) وأدخلنا حقلين بتنسيق تاريخ محدد.

## الخطوة 3: تغيير مصدر ثقافة التحديث الميداني
لتغيير مصدر ثقافة التحديث الميداني، استخدم فئة FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

في هذا المثال، قمنا بتعيين الثقافة المستخدمة أثناء التحديث الميداني ليتم اختيارها من الثقافة المستخدمة بواسطة الحقل.

## الخطوة 4: تنفيذ دمج البريد
قم بإجراء عملية دمج البريد وحدد قيمة التاريخ للحقل "Date2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

في مقتطف التعليمات البرمجية هذا، نقوم بتنفيذ عملية دمج البريد وتوفير قيمة DateTime للحقل "Date2".

## الخطوة 5: احفظ المستند
احفظ المستند المعدل في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### مثال على التعليمات البرمجية المصدر لتغيير مصدر ثقافة التحديث الميداني باستخدام Aspose.Words لـ .NET
فيما يلي التعليمات البرمجية المصدر الكاملة لتغيير مصدر ثقافة التحديث الميداني في مستندات Word باستخدام Aspose.Words لـ .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تغيير مصدر ثقافة التحديث الميداني في مستندات Word باستخدام Aspose.Words لـ .NET. باتباع الدليل خطوة بخطوة واستخدام التعليمات البرمجية المصدر المتوفرة، يمكنك الآن التحكم في الثقافة المستخدمة لتنسيق التاريخ أثناء عمليات التحديث الميداني ودمج البريد. قم بتخصيص مصدر الثقافة وفقًا لمتطلباتك لضمان تاريخ دقيق ومتسق.

### الأسئلة الشائعة

#### س: كيف يمكنني تغيير مصدر ثقافة التحديث الميداني في Aspose.Words لـ .NET؟

 ج: لتغيير مصدر ثقافة التحديث الميداني في Aspose.Words لـ .NET، يمكنك استخدام`Document.FieldOptions.CultureSource` الممتلكات وتحديد قيمتها`FieldCultureSource.FieldCode` أو`FieldCultureSource.CurrentThread` . على سبيل المثال، يمكنك استخدام`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` لاستخدام الثقافة المحددة في رمز الحقل.

#### س: كيف يمكنني تحديد ثقافة معينة لتحديث الحقول في Aspose.Words لـ .NET؟

ج: لتحديد ثقافة معينة لتحديث الحقول في Aspose.Words لـ .NET، يمكنك استخدام`Document.FieldOptions.FieldUpdateCultureInfo` الملكية وتعيين`CultureInfo` الكائن المطابق للثقافة المطلوبة. على سبيل المثال، يمكنك استخدام`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` لتحديد الثقافة الفرنسية (فرنسا).

#### س: هل من الممكن تعطيل التحديث الميداني التلقائي في Aspose.Words لـ .NET؟

 ج: نعم، من الممكن تعطيل التحديث الميداني التلقائي في Aspose.Words لـ .NET. يمكنك استخدام ال`Document.FieldOptions.UpdateFields` الملكية وتعيينها على`false` لمنع الحقول من التحديث التلقائي. يتيح لك ذلك التحكم يدويًا في تحديث الحقول حسب الحاجة.

#### س: كيف يمكنني تحديث حقول المستندات يدويًا في Aspose.Words لـ .NET؟

 ج: لتحديث الحقول يدويًا في مستند في Aspose.Words لـ .NET، يمكنك استخدام`Field.Update` الطريقة لكل مجال على حدة على سبيل المثال، يمكنك استخدام`field.Update()` لتحديث الحقل المحدد.