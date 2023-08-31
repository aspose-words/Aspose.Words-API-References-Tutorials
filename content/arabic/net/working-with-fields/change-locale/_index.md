---
title: تغيير اللغة
linktitle: تغيير اللغة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تغيير الإعدادات المحلية لتنسيق التاريخ والأرقام في مستندات Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fields/change-locale/
---

في هذا البرنامج التعليمي، سنرشدك خلال عملية تغيير الإعدادات المحلية في مستندات Word باستخدام Aspose.Words for .NET. من خلال تعديل الإعدادات المحلية، يمكنك التحكم في تنسيق التواريخ والأرقام أثناء عمليات دمج البريد. سنزودك بكود مصدر C# الضروري والتعليمات خطوة بخطوة لتحقيق ذلك.

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

## الخطوة 2: أدخل حقل
بعد ذلك، قم بإدراج حقل دمج في المستند باستخدام طريقة InsertField:

```csharp
builder.InsertField("MERGEFIELD Date");
```

في الكود أعلاه، نقوم بإدراج حقل دمج يسمى "التاريخ" في المستند.

## الخطوة 3: تغيير اللغة
لتغيير الإعدادات المحلية لتنسيق التاريخ والأرقام، يمكنك تعديل الثقافة الحالية لمؤشر الترابط. في هذا المثال، سنقوم بتعيين اللغة إلى الألمانية ("de-DE"):

```csharp
CultureInfo currentCulture = Thread.CurrentThread.CurrentCulture;
Thread.CurrentThread.CurrentCulture = new CultureInfo("de-DE");
```

في الكود أعلاه، نقوم بتخزين الثقافة الحالية ثم نقوم بتعيين ثقافة الخيط الحالي على اللغة الألمانية.

## الخطوة 4: تنفيذ دمج البريد
تنفيذ عملية دمج البريد وتوفير قيمة التاريخ لحقل "التاريخ":

```csharp
doc.MailMerge.Execute(new[] { "Date" }, new object[] { DateTime.Now });
```

في مقتطف التعليمات البرمجية هذا، نقوم بتنفيذ عملية دمج البريد وتوفير التاريخ الحالي كقيمة لحقل "التاريخ".

## الخطوة 5: استعادة اللغة الأصلية
بعد اكتمال دمج المراسلات، قم باستعادة الثقافة الأصلية لمؤشر الترابط:

```csharp
Thread.CurrentThread.CurrentCulture = currentCulture;
```

في الكود أعلاه، نستعيد الثقافة الأصلية للخيط.

## الخطوة 6: احفظ المستند
احفظ المستند المعدل في ملف باستخدام طريقة الحفظ لفئة المستند:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeLocale.docx");
```

### مثال على كود المصدر لتغيير اللغة باستخدام Aspose.Words لـ .NET
فيما يلي الكود المصدري الكامل لتغيير الإعدادات المحلية في مستندات Word باستخدام Aspose.Words لـ .NET:

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
تهانينا! لقد تعلمت بنجاح كيفية تغيير الإعدادات المحلية في مستندات Word باستخدام Aspose.Words لـ .NET. باتباع الدليل خطوة بخطوة واستخدام التعليمات البرمجية المصدر المتوفرة، يمكنك الآن التحكم في تنسيق التواريخ والأرقام أثناء عمليات دمج البريد. قم بتخصيص اللغة وفقًا لمتطلباتك لضمان التنسيق الدقيق والمتسق في مستنداتك.

### الأسئلة الشائعة

#### س: هل Aspose.Words متوافق مع إصدارات مختلفة من Microsoft Word؟

ج: نعم، Aspose.Words متوافق مع إصدارات مختلفة من Microsoft Word بما في ذلك Word 2003 وWord 2007 وWord 2010 وWord 2013 وWord 2016 وWord 2019.

#### س: هل يدعم Aspose.Words الهياكل الميدانية المعقدة؟

ج: بالتأكيد! يقدم Aspose.Words دعمًا شاملاً لهياكل الحقول المعقدة، بما في ذلك الحقول المتداخلة والحسابات والتعبيرات الشرطية. يمكنك استخدام واجهة برمجة التطبيقات القوية هذه للعمل مع أي نوع من بنية المجال.

#### س: هل يدعم Aspose.Words عمليات التحديث الميداني؟

ج: نعم، يسمح لك Aspose.Words بتحديث الحقول وفقًا لجدول زمني. يمكنك بسهولة تحديث قيم الحقول وتحديث العمليات الحسابية وتنفيذ العمليات الأخرى المتعلقة بالحقل باستخدام واجهة برمجة التطبيقات.

#### س: هل من الممكن تحويل الحقول إلى نص عادي باستخدام Aspose.Words؟

ج: بالتأكيد! يوفر Aspose.Words طرقًا لتحويل الحقول إلى نص عادي. يمكن أن يكون هذا مفيدًا عندما تحتاج إلى استخراج المحتوى دون أي تنسيق أو وظائف متعلقة بالحقل.

#### س: هل من الممكن إنشاء مستندات Word ذات حقول ديناميكية باستخدام Aspose.Words؟

ج: بالتأكيد! يوفر Aspose.Words وظائف قوية لإنشاء مستندات Word ذات حقول ديناميكية. يمكنك إنشاء قوالب بحقول محددة مسبقًا وملؤها بالبيانات ديناميكيًا، مما يوفر حلاً مرنًا وفعالاً لإنشاء المستندات.