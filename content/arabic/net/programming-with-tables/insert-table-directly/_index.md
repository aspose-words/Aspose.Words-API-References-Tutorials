---
title: إدراج الجدول مباشرة
linktitle: إدراج الجدول مباشرة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج الجداول مباشرةً في مستندات Word باستخدام Aspose.Words لـ .NET. اتبع دليلنا التفصيلي خطوة بخطوة لتبسيط إنشاء المستندات الخاصة بك.
type: docs
weight: 10
url: /ar/net/programming-with-tables/insert-table-directly/
---
## مقدمة
يمكن أن يمثل إنشاء الجداول برمجيًا تحديًا كبيرًا، خاصة عند التعامل مع هياكل المستندات المعقدة. لكن لا تقلق، نحن هنا لنشرح لك الأمر! في هذا الدليل، سنتعرف على خطوات إدراج جدول مباشرةً في مستند Word باستخدام Aspose.Words for .NET. سواء كنت مطورًا متمرسًا أو بدأت للتو، سيساعدك هذا البرنامج التعليمي على إتقان العملية بسهولة.

## المتطلبات الأساسية

قبل الغوص في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه للبدء. فيما يلي قائمة مرجعية سريعة:

1.  Aspose.Words لمكتبة .NET: تأكد من تنزيل وتثبيت مكتبة Aspose.Words لـ .NET. يمكنك الحصول عليه من[صفحة التحميل](https://releases.aspose.com/words/net/).
2. بيئة التطوير: بيئة تطوير مثل Visual Studio.
3. المعرفة الأساسية بـ C#: فهم أساسيات برمجة C#.
4. دليل المستندات: مسار الدليل الذي ستحفظ فيه مستنداتك.

مع توفر هذه المتطلبات الأساسية، أنت جاهز لبدء البرمجة!

## استيراد مساحات الأسماء

أولاً، لنستورد مساحات الأسماء الضرورية. ستزودنا مساحات الأسماء هذه بالفئات والأساليب اللازمة للعمل مع مستندات Word.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

الآن وبعد أن أصبح لدينا مساحات الأسماء في مكانها الصحيح، فلننتقل إلى الجزء المثير — وهو إنشاء الجداول وإدراجها مباشرة في مستند Word.

## الخطوة 1: إعداد الوثيقة

لنبدأ بإعداد مستند Word جديد. هذا هو المكان الذي سيتم إدراج جدولنا فيه.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 يقوم هذا الرمز بتهيئة مستند Word جديد. سوف تحتاج إلى استبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

## الخطوة 2: إنشاء كائن الجدول

بعد ذلك، نقوم بإنشاء كائن الجدول. هذا هو المكان الذي سنحدد فيه هيكل طاولتنا.

```csharp
// نبدأ بإنشاء كائن الجدول. لاحظ أنه يجب علينا تمرير كائن المستند
// إلى منشئ كل عقدة. وذلك لأن كل عقدة نقوم بإنشائها يجب أن تنتمي
// إلى بعض الوثيقة.
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

هنا، نقوم بإنشاء جدول جديد وإلحاقه بنص القسم الأول من وثيقتنا.

## الخطوة 3: إضافة الصفوف والخلايا

يتكون الجدول من صفوف وخلايا. دعونا نضيف هذه العناصر خطوة بخطوة.

### إضافة صف

```csharp
// هنا يمكننا الاتصال بـ EnsureMinimum لإنشاء الصفوف والخلايا لنا. يتم استخدام هذه الطريقة
// للتأكد من صحة العقدة المحددة. في هذه الحالة، يجب أن يحتوي الجدول الصالح على صف واحد وخلية واحدة على الأقل.
// وبدلاً من ذلك، سنتولى إنشاء الصف والجدول بأنفسنا.
// ستكون هذه أفضل طريقة للقيام بذلك إذا كنا نقوم بإنشاء جدول داخل خوارزمية.
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);
```

يقوم هذا الرمز بإنشاء صف جديد وإلحاقه بجدولنا.

### إضافة خلايا إلى الصف

الآن، دعونا نضيف بعض الخلايا إلى صفنا. 

```csharp
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
row.AppendChild(cell);
```

في هذا المقتطف، نقوم بإنشاء خلية، ونضبط لون خلفيتها على اللون الأزرق الفاتح، ونحدد عرضها. بعد ذلك، نضيف فقرة ونركض إلى الخلية للاحتفاظ بالنص.

## الخطوة 4: استنساخ الخلايا

لتسريع عملية إضافة الخلايا، يمكننا استنساخ الخلايا الموجودة.

```csharp
// ثم نكرر العملية مع الخلايا والصفوف الأخرى في الجدول.
//يمكننا أيضًا تسريع الأمور عن طريق استنساخ الخلايا والصفوف الموجودة.
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
```

يقوم هذا الرمز باستنساخ الخلية الموجودة وإضافتها إلى الصف. ثم نقوم بإضافة فقرة وتشغيل إلى الخلية الجديدة.

## الخطوة 5: تطبيق إعدادات الاحتواء التلقائي

وأخيرًا، دعونا نطبق إعدادات الاحتواء التلقائي على جدولنا للتأكد من أن عرض الأعمدة ثابت.

```csharp
// يمكننا الآن تطبيق أي إعدادات ملائمة تلقائية.
table.AutoFit(AutoFitBehavior.FixedColumnWidths);
```

## الخطوة 6: حفظ المستند

بعد أن تم إعداد طاولتنا بالكامل، حان الوقت لحفظ المستند.

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

يحفظ هذا الرمز المستند مع الجدول المدرج.

## خاتمة

تهانينا! لقد نجحت في إدراج جدول مباشرةً في مستند Word باستخدام Aspose.Words لـ .NET. يمكن استخدام هذه العملية لإنشاء جداول معقدة برمجيًا، مما يجعل مهام أتمتة المستندات الخاصة بك أسهل بكثير. سواء كنت تقوم بإنشاء تقارير أو فواتير أو أي نوع آخر من المستندات، فإن فهم كيفية التعامل مع الجداول يعد مهارة بالغة الأهمية.

## الأسئلة الشائعة

### كيف يمكنني تنزيل Aspose.Words لـ .NET؟
 يمكنك تنزيل Aspose.Words لـ .NET من[صفحة التحميل](https://releases.aspose.com/words/net/).

### هل يمكنني تجربة Aspose.Words لـ .NET قبل الشراء؟
 نعم يمكنك طلب أ[تجربة مجانية](https://releases.aspose.com/) لتقييم المكتبة قبل الشراء.

### كيف يمكنني شراء Aspose.Words لـ .NET؟
يمكنك شراء Aspose.Words لـ .NET من[صفحة الشراء](https://purchase.aspose.com/buy).

### أين يمكنني العثور على الوثائق الخاصة بـ Aspose.Words لـ .NET؟
 الوثائق متاحة[هنا](https://reference.aspose.com/words/net/).

### ماذا لو كنت بحاجة إلى الدعم أثناء استخدام Aspose.Words لـ .NET؟
 للحصول على الدعم، يمكنك زيارة[منتدى Aspose.Words](https://forum.aspose.com/c/words/8).