---
title: تغيير نمط Toc في مستند Word
linktitle: تغيير نمط Toc في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية تغيير نمط مستوى جدول المحتويات بسهولة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-of-content/change-style-of-toc-level/
---
Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها ومعالجتها في تطبيق C #. من بين الميزات التي تقدمها Aspose.Words القدرة على تغيير نمط مستوى معين من جدول محتويات المستند. في هذا الدليل ، سنوضح لك كيفية استخدام الكود المصدري C # الخاص بـ Aspose.Words for .NET لتغيير نمط مستوى جدول محتويات مستند Word.

## فهم مكتبة Aspose.Words

قبل التعمق في الكود ، من المهم فهم مكتبة Aspose.Words لـ .NET. Aspose.Words مكتبة شائعة تجعل معالجة الكلمات بمستندات Word سهلة وفعالة. يوفر مجموعة واسعة من الميزات لإنشاء مستندات Word وتحريرها ومعالجتها ، بما في ذلك تغيير نمط جدول المحتويات.

## إنشاء وثيقة جديدة

تتمثل الخطوة الأولى في إنشاء مستند Word جديد حيث تريد تغيير نمط جدول المحتويات. استخدم فئة المستند لإنشاء مستند جديد. هنا مثال :

```csharp
Document doc = new Document();
```

في هذا المثال ، نقوم بإنشاء مستند فارغ جديد.

## تغيير نمط جدول المحتويات

بمجرد إنشاء المستند ، يمكنك الوصول إلى أنماط المستند وتغيير النمط المستخدم لمستوى معين من جدول المحتويات. في هذا المثال ، سنقوم بتعديل النمط المستخدم للمستوى الأول من جدول المحتويات. إليك الطريقة:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

في هذا المثال ، نستخدم خاصية Styles لفئة Document للوصول إلى أنماط المستند. بعد ذلك ، نستخدم معرف النمط StyleIdentifier.Toc1 للوصول إلى النمط المستخدم للمستوى الأول من جدول المحتويات. أخيرًا ، نقوم بتعديل الخاصية Font.Bold للنمط لجعلها غامقة.

## احفظ المستند المعدل

بمجرد إجراء التعديلات اللازمة على نمط جدول المحتويات ، يمكنك حفظ المستند المعدل باستخدام طريقة Save لفئة Document. هنا مثال :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

في هذا المثال ، نحفظ المستند المعدل باسم "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## مثال على شفرة المصدر لميزة "تغيير نمط مستوى جدول المحتويات" باستخدام Aspose.Words for .NET

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بإنشاء مستند جديد
Document doc = new Document();

// تعديل نمط المستوى الأول لجدول المحتويات
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// احفظ المستند المعدل
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## خاتمة

في هذا الدليل ، شرحنا كيفية استخدام Aspose.Words for .NET لتغيير نمط مستوى جدول محتويات مستند Word باستخدام كود المصدر C # المقدم. باتباع الخطوات المقدمة ، يمكنك بسهولة تخصيص نمط جدول المحتويات في مستندات Word الخاصة بك في تطبيق C # الخاص بك. يوفر Aspose.Words مرونة وقوة هائلة للعمل مع أنماط وتنسيقات مستنداتك ، مما يسمح لك بإنشاء مستندات Word جذابة واحترافية.

### الأسئلة الشائعة لتغيير نمط toc في مستند Word

#### س: ما هو الغرض من وظيفة "تغيير نمط Toc في مستند Word" في Aspose.Words for .NET؟

ج: تسمح لك وظيفة "تغيير نمط Toc في مستند Word" في Aspose.Words for .NET بتعديل نمط مستوى معين في جدول محتويات مستند Word. يمكّنك من تخصيص مظهر وتنسيق جدول المحتويات ، مثل تغيير نمط الخط أو الحجم أو اللون أو الجوانب المرئية الأخرى لمستوى معين.

#### س: ما المقصود بـ Aspose.Words لـ .NET؟

ج: Aspose.Words for .NET مكتبة قوية مصممة لمعالجة الكلمات باستخدام مستندات Word في تطبيقات .NET. يوفر ميزات شاملة لإنشاء مستندات Word وتحريرها ومعالجتها وتحويلها برمجيًا باستخدام C # أو لغات .NET الأخرى.

#### س: كيف أقوم بإنشاء مستند Word جديد باستخدام Aspose.Words for .NET؟

 ج: لإنشاء مستند Word جديد باستخدام Aspose.Words for .NET ، يمكنك استخدام`Document` الطبقة ومنشئها. من خلال تهيئة مثيل جديد لـ`Document` فئة ، يمكنك إنشاء مستند فارغ. هذا مثال:

```csharp
Document doc = new Document();
```

يُنشئ مقتطف الشفرة هذا مستند Word فارغًا جديدًا.

#### س: كيف يمكنني تغيير نمط مستوى معين في جدول المحتويات باستخدام Aspose.Words for .NET؟

 ج: بمجرد تحميل المستند ، يمكنك تعديل نمط مستوى معين في جدول المحتويات عن طريق الوصول إلى أنماط المستند وإجراء التغييرات اللازمة. في Aspose.Words for .NET ، يمكنك استخدام ملحق`Styles` ممتلكات`Document` class للوصول إلى أنماط المستند ، ثم قم بتعديل النمط المطلوب باستخدام خصائصه. على سبيل المثال ، لتغيير نمط المستوى الأول من جدول المحتويات إلى غامق ، يمكنك استخدام الكود التالي:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

 في هذا الكود ،`doc.Styles[StyleIdentifier.Toc1]` يصل إلى نمط المستوى الأول من جدول المحتويات ، و`Font.Bold = true` يحدد نمط الخط الغامق لهذا النمط.

#### س: هل يمكنني تغيير نمط المستويات المتعددة في جدول المحتويات باستخدام Aspose.Words for .NET؟

 ج: نعم ، يمكنك تغيير نمط المستويات المتعددة في جدول المحتويات باستخدام Aspose.Words for .NET. لتعديل نمط مستوى معين ، يمكنك الوصول إلى النمط المقابل باستخدام`Styles`الملكية وإجراء التغييرات المطلوبة على كل مستوى على حدة.

#### س: كيف يمكنني حفظ المستند المعدل بعد تغيير نمط جدول المحتويات باستخدام Aspose.Words for .NET؟

 ج: بمجرد إجراء التعديلات اللازمة على نمط جدول المحتويات ، يمكنك حفظ المستند المعدل باستخدام`Save` طريقة`Document` فصل. حدد مسار الملف المطلوب واسم مستند الإخراج كمعامل لملف`Save` طريقة. هذا مثال:

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

يحفظ هذا الرمز المستند المعدل كـ "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

#### س: هل يمكنني تطبيق تغييرات تنسيق أخرى على جدول المحتويات باستخدام Aspose.Words for .NET؟

ج: نعم ، بالإضافة إلى تغيير النمط ، يمكنك تطبيق تغييرات تنسيق مختلفة على جدول المحتويات باستخدام Aspose.Words for .NET. على سبيل المثال ، يمكنك تعديل حجم الخط أو اللون أو المحاذاة أو إضافة خصائص تنسيق إضافية لتحسين مظهر جدول المحتويات.

#### س: كيف يمكنني تحديد نمط مخصص لمستوى معين في جدول المحتويات باستخدام Aspose.Words for .NET؟

 ج: لتحديد نمط مخصص لمستوى معين في جدول المحتويات باستخدام Aspose.Words for .NET ، يمكنك إنشاء`Style` الكائن ، قم بتكوين خصائصه وفقًا للنمط الذي تريده ، وقم بتعيينه إلى المستوى المقابل لجدول المحتويات باستخدام`Styles` ممتلكات`Document` فصل. يتيح لك هذا تحديد نمط مخصص لمستوى معين بناءً على متطلباتك.

#### س: هل يمكنني تغيير نمط جدول المحتويات في مستند Word موجود باستخدام Aspose.Words for .NET؟

 ج: نعم ، يمكنك تغيير نمط جدول المحتويات في مستند Word موجود باستخدام Aspose.Words for .NET. ما عليك سوى تحميل المستند باستخدام ملف`Document` class ، قم بتعديل خصائص النمط باستخدام`Styles` الخاصية ، وحفظ المستند لتطبيق التغييرات.

#### س: هل يدعم Aspose.Words for .NET تغيير الأنماط والتنسيق الأخرى في مستندات Word؟

ج: نعم ، يوفر Aspose.Words for .NET دعمًا شاملاً لتغيير أنماط وتنسيقات مختلفة في مستندات Word. يسمح لك بتعديل الأنماط لعناصر مختلفة مثل الفقرات والعناوين والجداول والقوائم والمزيد. يمكنك تغيير الخطوط والألوان والمحاذاة والمسافة البادئة والتباعد وجوانب التنسيق الأخرى وفقًا لمتطلباتك.