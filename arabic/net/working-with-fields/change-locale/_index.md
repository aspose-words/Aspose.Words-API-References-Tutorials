---
title: تغيير اللغة
linktitle: تغيير اللغة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تغيير الإعدادات المحلية لتنسيق التاريخ والأرقام في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/change-locale/
---

في هذا البرنامج التعليمي ، سنوجهك خلال عملية تغيير الإعدادات المحلية في مستندات Word باستخدام Aspose.Words for .NET. من خلال تعديل الإعدادات المحلية ، يمكنك التحكم في تنسيق التواريخ والأرقام أثناء عمليات دمج البريد. سنزودك بشفرة المصدر C # الضرورية والتعليمات خطوة بخطوة لتحقيق ذلك.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند و DocumentBuilder
للبدء ، قم بإنشاء مثيل لفئة Document وكائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل حقل
بعد ذلك ، أدخل حقل دمج في المستند باستخدام طريقة InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

في الكود أعلاه ، نقوم بإدراج حقل دمج يسمى "التاريخ" في المستند.

## الخطوة 3: قم بتغيير اللغة
لتغيير لغة تنسيق التاريخ والأرقام ، يمكنك تعديل الثقافة الحالية لمؤشر الترابط. في هذا المثال ، سنقوم بتعيين اللغة إلى الألمانية ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

في الكود أعلاه ، نقوم بتخزين الثقافة الحالية ثم نقوم بتعيين ثقافة الخيط الحالي على اللغة الألمانية.

## الخطوة 4: قم بإجراء دمج المراسلات
نفّذ عملية دمج المراسلات وقدم قيمة التاريخ لحقل "التاريخ":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

في مقتطف الشفرة هذا ، ننفذ عملية دمج المراسلات ونقدم التاريخ الحالي كقيمة لحقل "التاريخ".

## الخطوة 5: استعادة الإعدادات المحلية الأصلية
بعد اكتمال دمج المراسلات ، قم باستعادة البيانات الموروثة الأصلية لمؤشر الترابط:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

في الكود أعلاه ، نقوم باستعادة الثقافة الأصلية للخيط.

## الخطوة 6: احفظ المستند
احفظ المستند المعدل في ملف باستخدام طريقة Save لفئة Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### مثال على كود المصدر لتغيير اللغة باستخدام Aspose.Words for .NET
فيما يلي رمز المصدر الكامل لتغيير اللغة في مستندات Word باستخدام Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField("MERGEFIELD Date");

CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");

doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });

Thread.CurrentThread.CurrentCulture = currentCulture;

doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

## خاتمة
تهانينا! لقد تعلمت بنجاح كيفية تغيير اللغة في مستندات Word باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك الآن التحكم في تنسيق التواريخ والأرقام أثناء عمليات دمج المراسلات. قم بتخصيص الإعدادات المحلية وفقًا لمتطلباتك لضمان التنسيق الدقيق والمتسق في مستنداتك.

### التعليمات

#### س: هل Aspose.Words متوافق مع إصدارات مختلفة من Microsoft Word؟

ج: نعم ، Aspose.Words متوافق مع إصدارات مختلفة من Microsoft Word بما في ذلك Word 2003 و Word 2007 و Word 2010 و Word 2013 و Word 2016 و Word 2019.

#### س: هل تدعم Aspose.Words الهياكل الميدانية المعقدة؟

ج: إطلاقا! تقدم Aspose.Words دعمًا شاملاً لهياكل الحقول المعقدة ، بما في ذلك الحقول المتداخلة والحسابات والتعبيرات الشرطية. يمكنك استخدام واجهة برمجة التطبيقات القوية هذه للعمل مع أي نوع من الهياكل الميدانية.

#### س: هل تدعم Aspose.Words عمليات التحديث الميداني؟

ج: نعم ، تسمح لك Aspose.Words بتحديث الحقول وفقًا لجدول زمني. يمكنك بسهولة تحديث قيم الحقول ، وتحديث الحسابات ، وتنفيذ العمليات الأخرى ذات الصلة بالحقل باستخدام API.

#### س: هل من الممكن تحويل الحقول إلى نص عادي باستخدام Aspose.Words؟

ج: بالتأكيد! يوفر Aspose.Words طرق لتحويل الحقول إلى نص عادي. يمكن أن يكون هذا مفيدًا عندما تحتاج إلى استخراج المحتوى بدون أي تنسيق أو وظيفة ذات صلة بالمجال.

#### س: هل من الممكن إنشاء مستندات Word بحقول ديناميكية باستخدام Aspose.Words؟

ج: إطلاقا! يوفر Aspose.Words وظائف قوية لإنشاء مستندات Word بحقول ديناميكية. يمكنك إنشاء قوالب بحقول محددة مسبقًا وملؤها بالبيانات ديناميكيًا ، مما يوفر حلاً مرنًا وفعالًا لإنشاء المستندات.