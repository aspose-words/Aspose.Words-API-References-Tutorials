---
title: استبدال النص في الجدول
linktitle: استبدال النص في الجدول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استبدال النص في جدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/find-and-replace-text/replace-text-in-table/
---

في هذه المقالة، سوف نستكشف كود مصدر C# أعلاه لفهم كيفية استخدام وظيفة استبدال النص في الجدول في Aspose.Words لمكتبة .NET. تتيح لك هذه الميزة البحث عن نص معين واستبداله داخل جدول في مستند Word.

## المتطلبات الأساسية

- المعرفة الأساسية بلغة C#.
- بيئة تطوير .NET مع تثبيت مكتبة Aspose.Words.

## الخطوة 1: قم بتحميل المستند

 قبل أن نبدأ في استخدام استبدال النص في الجدول، نحتاج إلى تحميل المستند إلى Aspose.Words لـ .NET. ويمكن القيام بذلك باستخدام`Document` فئة وتحديد مسار ملف الوثيقة:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 2: الوصول إلى اللوحة

 بمجرد تحميل المستند، نحتاج إلى الانتقال إلى الجدول حيث نريد إجراء استبدال النص. في مثالنا، نستخدم`GetChild` الطريقة مع`NodeType.Table` المعلمة للحصول على الجدول الأول في المستند:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## الخطوة 3: إجراء استبدال النص

 الآن نستخدم`Range.Replace` طريقة لإجراء استبدال النص في المصفوفة. في مثالنا، نستبدل كل تكرارات كلمة "Carrots" بكلمة "Eggs" باستخدام`FindReplaceOptions` الخيار مع`FindReplaceDirection.Forward` اتجاه البحث. بالإضافة إلى ذلك، نستبدل القيمة "50" بالقيمة "20" في الخلية الأخيرة من الصف الأخير من الجدول:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## الخطوة 4: احفظ المستند الذي تم تحريره

 وأخيرًا، نقوم بحفظ المستند المعدل في دليل محدد باستخدام الملف`Save` طريقة:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words for .NET لقد اتبعنا دليلاً خطوة بخطوة لتحميل مستند والوصول إلى الجدول وإجراء استبدال النص وحفظ المستند المعدل.

### مثال على التعليمات البرمجية المصدر لاستبدال النص في الجدول باستخدام Aspose.Words لـ .NET

فيما يلي نموذج التعليمات البرمجية المصدر الكامل لتوضيح استخدام استبدال النص في جدول باستخدام Aspose.Words لـ .NET:

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

في هذه المقالة، استكشفنا الكود المصدري لـ C# لفهم كيفية استخدام وظيفة استبدال النص في الجدول في Aspose.

### الأسئلة الشائعة

#### س: ما هي ميزة "استبدال النص في الجدول" في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة "استبدال النص في الجدول" في Aspose.Words لـ .NET إمكانية البحث عن نص معين واستبداله داخل جدول في مستند Word. فهو يمكّنك من تحديد كلمات أو عبارات أو أنماط محددة داخل جدول واستبدالها بالمحتوى المطلوب.

#### س: كيف يمكنني تحميل مستند Word باستخدام Aspose.Words لـ .NET؟

ج: لتحميل مستند Word باستخدام Aspose.Words لـ .NET، يمكنك استخدام`Document` فئة وحدد مسار ملف الوثيقة. فيما يلي مثال على كود C# لتحميل مستند:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

#### س: كيف يمكنني الوصول إلى جدول في مستند باستخدام Aspose.Words for .NET؟

ج: بمجرد تحميل المستند، يمكنك الوصول إلى الجدول الذي تريد إجراء استبدال النص فيه. في Aspose.Words for .NET، يمكنك استخدام`GetChild` الطريقة مع`NodeType.Table` المعلمة للحصول على الجدول المطلوب. على سبيل المثال:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

#### س: كيف يمكنني إجراء استبدال النص داخل جدول باستخدام Aspose.Words for .NET؟

 ج: لإجراء استبدال النص داخل جدول باستخدام Aspose.Words لـ .NET، يمكنك استخدام`Range.Replace` طريقة على نطاق الجدول. تتيح لك هذه الطريقة تحديد النص المطلوب البحث عنه والنص البديل. هنا مثال:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### س: هل يمكنني إجراء استبدال النص في خلية معينة من الجدول باستخدام Aspose.Words لـ .NET؟

ج: نعم، يمكنك إجراء استبدال النص في خلية معينة من الجدول باستخدام Aspose.Words لـ .NET. بعد الوصول إلى الجدول، يمكنك الانتقال إلى الخلية المطلوبة وتطبيق عملية استبدال النص على نطاقها. على سبيل المثال:

```csharp
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### س: هل يمكنني استخدام التعبيرات العادية لاستبدال النص في جدول باستخدام Aspose.Words for .NET؟

ج: نعم، يمكنك استخدام التعبيرات العادية لاستبدال النص في جدول باستخدام Aspose.Words لـ .NET. من خلال إنشاء نمط تعبير عادي، يمكنك إجراء مطابقة أكثر تقدمًا ومرونة لاستبدال النص داخل الجدول. يتيح لك ذلك التعامل مع أنماط البحث المعقدة وإجراء عمليات الاستبدال الديناميكية بناءً على المجموعات أو الأنماط التي تم التقاطها.

#### س: هل هناك أي قيود أو اعتبارات عند استبدال النص في جدول باستخدام Aspose.Words for .NET؟

ج: عند استبدال نص في جدول باستخدام Aspose.Words لـ .NET، من المهم مراعاة تنسيق الجدول وبنيته. إذا كان النص البديل يختلف بشكل كبير في الطول أو التنسيق، فقد يؤثر ذلك على تخطيط الجدول ومظهره. تأكد من أن النص البديل يتماشى مع تصميم الجدول للحفاظ على نتيجة متسقة وممتعة بصريًا.

#### س: هل يمكنني استبدال النص في جداول متعددة داخل مستند باستخدام Aspose.Words for .NET؟

ج: نعم، يمكنك استبدال النص في جداول متعددة داخل المستند باستخدام Aspose.Words for .NET. يمكنك التكرار على الجداول الموجودة في المستند وتنفيذ عملية استبدال النص في كل جدول على حدة. يتيح لك ذلك استبدال نص معين في كافة الجداول الموجودة في المستند.

#### س: ما الذي يوضحه مثال التعليمات البرمجية المصدر لميزة "استبدال النص في الجدول" في Aspose.Words لـ .NET؟

ج: يوضح مثال التعليمات البرمجية المصدر استخدام ميزة "استبدال النص في الجدول" في Aspose.Words لـ .NET. فهو يوضح كيفية تحميل مستند، والوصول إلى جدول معين، وإجراء استبدال النص داخل الجدول، وحفظ المستند المعدل.

#### س: هل يمكنني إجراء عمليات أخرى على الجداول باستخدام Aspose.Words لـ .NET؟

ج: نعم، يمكنك إجراء عمليات متنوعة على الجداول باستخدام Aspose.Words لـ .NET. تتضمن بعض العمليات الشائعة إضافة صفوف أو إزالتها، ودمج الخلايا، وضبط تنسيق الجدول، وتعيين محتوى الخلية، وغير ذلك الكثير. يوفر Aspose.Words مجموعة غنية من واجهات برمجة التطبيقات للتعامل مع الجداول ومحتوياتها بسهولة ومرونة.