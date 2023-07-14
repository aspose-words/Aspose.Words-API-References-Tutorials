---
title: استبدال النص في الجدول
linktitle: استبدال النص في الجدول
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استبدال نص في جدول في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/replace-text-in-table/
---

في هذه المقالة ، سوف نستكشف الكود المصدري C # أعلاه لفهم كيفية استخدام وظيفة "استبدال النص في الجدول" في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة البحث عن نص معين واستبداله داخل جدول في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية للغة C #.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: قم بتحميل المستند

 قبل أن نبدأ في استخدام استبدال النص في جدول ، نحتاج إلى تحميل المستند إلى Aspose.Words for .NET. يمكن القيام بذلك باستخدام ملف`Document` فئة وتحديد مسار ملف المستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 2: الوصول إلى اللوحة

 بمجرد تحميل المستند ، نحتاج إلى الانتقال إلى الجدول حيث نريد إجراء استبدال النص. في مثالنا ، نستخدم الامتداد`GetChild` الطريقة مع`NodeType.Table` المعلمة للحصول على الجدول الأول في المستند:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## الخطوة 3: إجراء استبدال النص

 الآن نستخدم ملف`Range.Replace` طريقة لإجراء استبدال النص في المصفوفة. في مثالنا ، نستبدل كل تكرارات كلمة "Carrots" بكلمة "Eggs" باستخدام امتداد`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث. بالإضافة إلى ذلك ، نستبدل القيمة "50" بـ "20" في الخلية الأخيرة من الصف الأخير من الجدول:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: احفظ المستند المحرر

 أخيرًا ، نحفظ المستند المعدل في دليل محدد باستخدام امتداد`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words for .NET اتبعنا دليلًا تفصيليًا لتحميل مستند والوصول إلى الجدول وإجراء استبدال النص وحفظ المستند المعدل.

### مثال على شفرة المصدر لـ Replace Text In Table باستخدام Aspose.Words لـ .NET

في ما يلي نموذج التعليمات البرمجية المصدر الكامل لإثبات استخدام استبدال النص في جدول مع Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## خاتمة

في هذه المقالة ، استكشفنا الكود المصدري C # لفهم كيفية استخدام وظيفة Aspose's Replace Text In Table.

### التعليمات

#### س: ما هي ميزة "استبدال النص في الجدول" في Aspose.Words for .NET؟

ج: تسمح لك ميزة "استبدال النص في الجدول" في Aspose.Words for .NET بالعثور على نص معين واستبداله داخل جدول في مستند Word. يمكّنك من تحديد كلمات أو عبارات أو أنماط معينة داخل جدول واستبدالها بالمحتوى المطلوب.

#### س: كيف يمكنني تحميل مستند Word باستخدام Aspose.Words for .NET؟

ج: لتحميل مستند Word باستخدام Aspose.Words for .NET ، يمكنك استخدام`Document` class وحدد مسار ملف المستند. فيما يلي مثال على رمز C # لتحميل مستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

#### س: كيف يمكنني الوصول إلى جدول في مستند باستخدام Aspose.Words for .NET؟

ج: بمجرد تحميل المستند ، يمكنك الوصول إلى الجدول الذي تريد إجراء استبدال النص فيه. في Aspose.Words for .NET ، يمكنك استخدام ملحق`GetChild` الطريقة مع`NodeType.Table` المعلمة للحصول على الجدول المطلوب. على سبيل المثال:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

#### س: كيف يمكنني إجراء استبدال النص داخل جدول باستخدام Aspose.Words for .NET؟

 ج: لإجراء استبدال النص داخل جدول باستخدام Aspose.Words for .NET ، يمكنك استخدام`Range.Replace` الطريقة في نطاق الجدول. تسمح لك هذه الطريقة بتحديد النص الذي تريد البحث عنه والنص البديل. هذا مثال:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### س: هل يمكنني إجراء استبدال النص في خلية معينة من الجدول باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك إجراء استبدال النص في خلية معينة من الجدول باستخدام Aspose.Words for .NET. بعد الوصول إلى الجدول ، يمكنك الانتقال إلى الخلية المطلوبة وتطبيق عملية استبدال النص على نطاقها. على سبيل المثال:

```csharp
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### س: هل يمكنني استخدام التعبيرات العادية لاستبدال النص في جدول باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك استخدام التعبيرات العادية لاستبدال النص في جدول مع Aspose.Words for .NET. من خلال إنشاء نمط تعبير عادي ، يمكنك إجراء مطابقة أكثر تقدمًا ومرونة لاستبدال النص داخل الجدول. يتيح لك ذلك التعامل مع أنماط البحث المعقدة وإجراء عمليات الاستبدال الديناميكية بناءً على المجموعات أو الأنماط التي تم التقاطها.

#### س: هل هناك أي قيود أو اعتبارات عند استبدال نص في جدول باستخدام Aspose.Words for .NET؟

ج: عند استبدال نص في جدول باستخدام Aspose.Words لـ .NET ، من المهم مراعاة تنسيق الجدول وهيكله. إذا كان النص البديل يختلف اختلافًا كبيرًا في الطول أو التنسيق ، فقد يؤثر على تخطيط الجدول ومظهره. تأكد من أن النص البديل يتماشى مع تصميم الجدول للحفاظ على نتيجة متسقة وممتعة بصريًا.

#### س: هل يمكنني استبدال نص في جداول متعددة داخل مستند باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك استبدال نص في جداول متعددة داخل مستند باستخدام Aspose.Words for .NET. يمكنك تكرار الجداول الموجودة في المستند وتنفيذ عملية استبدال النص على كل جدول على حدة. يتيح لك هذا استبدال نص معين في جميع الجداول الموجودة في المستند.

#### س: ما الذي يوضحه مثال شفرة المصدر لميزة "استبدال النص في الجدول" في Aspose.Words for .NET؟

ج: يوضح مثال كود المصدر استخدام ميزة "استبدال النص في الجدول" في Aspose.Words for .NET. يوضح كيفية تحميل مستند ، والوصول إلى جدول معين ، واستبدال النص داخل الجدول ، وحفظ المستند المعدل.

#### س: هل يمكنني إجراء عمليات أخرى على الجداول باستخدام Aspose.Words for .NET؟

ج: نعم ، يمكنك إجراء عمليات مختلفة على الجداول باستخدام Aspose.Words for .NET. تتضمن بعض العمليات الشائعة إضافة صفوف أو إزالتها ودمج الخلايا وتعديل تنسيق الجدول وتعيين محتوى الخلية وغير ذلك الكثير. يوفر Aspose.Words مجموعة غنية من واجهات برمجة التطبيقات للتعامل مع الجداول ومحتوياتها بسهولة ومرونة.