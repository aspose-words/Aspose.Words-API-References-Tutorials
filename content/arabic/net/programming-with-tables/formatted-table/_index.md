---
title: جدول منسق
linktitle: جدول منسق
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إنشاء الجداول وتنسيقها في مستندات Word باستخدام Aspose.Words لـ .NET باستخدام هذا الدليل المفصل خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/programming-with-tables/formatted-table/
---
## مقدمة

قد يبدو إنشاء الجداول وتنسيقها في مستندات Word برمجيًا مهمة شاقة، ولكن مع Aspose.Words for .NET، تصبح هذه المهمة واضحة وسهلة الإدارة. في هذا البرنامج التعليمي، سنرشدك إلى كيفية إنشاء جدول منسق في مستند Word باستخدام Aspose.Words for .NET. سنغطي كل شيء بدءًا من إعداد بيئتك وحتى حفظ مستندك بجدول منسق بشكل جميل.

## المتطلبات الأساسية

قبل الغوص في الكود، دعنا نتأكد من أن لديك كل ما تحتاجه:

1. Aspose.Words لمكتبة .NET: قم بتنزيله من[هنا](https://releases.aspose.com/words/net/).
2. بيئة التطوير: بيئة تطوير متكاملة (IDE) مثل Visual Studio.
3. .NET Framework: تأكد من تثبيت .NET Framework على جهازك.

## استيراد مساحات الأسماء

قبل كتابة التعليمات البرمجية الفعلية، تحتاج إلى استيراد مساحات الأسماء الضرورية:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

أولاً، تحتاج إلى تحديد المسار الذي سيتم حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي الذي تريد حفظ المستند فيه.

## الخطوة 2: تهيئة المستند و DocumentBuilder

الآن، قم بتهيئة مستند جديد وكائن DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 ال`DocumentBuilder` هي فئة مساعدة تعمل على تبسيط عملية إنشاء المستندات.

## الخطوة 3: ابدأ الجدول

 بعد ذلك، ابدأ في إنشاء الجدول باستخدام`StartTable` طريقة.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

يعد إدراج خلية ضروريًا لبدء الجدول.

## الخطوة 4: تطبيق التنسيق على مستوى الجدول

يمكنك تطبيق التنسيق الذي يؤثر على الجدول بأكمله. على سبيل المثال، تعيين المسافة البادئة اليسرى:

```csharp
table.LeftIndent = 20.0;
```

## الخطوة 5: تنسيق صف الرأس

قم بتعيين الارتفاع والمحاذاة والخصائص الأخرى لصف الرأس.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

في هذه الخطوة، نجعل صف الرأس بارزًا عن طريق تعيين لون الخلفية وحجم الخط والمحاذاة.

## الخطوة 6: أدخل خلايا رأس إضافية

أدخل المزيد من الخلايا لصف الرأس:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## الخطوة 7: تنسيق صفوف الجسم

بعد إعداد الرأس، قم بتنسيق نص الجدول:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## الخطوة 8: إدراج صفوف الجسم

أدخل صفوف النص مع المحتوى:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

كرر للصفوف الإضافية:

```csharp
builder.InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Row 2, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 2, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 2, Cell 3 Content.");
builder.EndRow();
builder.EndTable();
```

## الخطوة 9: احفظ المستند

أخيرًا، احفظ المستند في الدليل المحدد:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

سيؤدي هذا إلى إنشاء مستند Word وحفظه بالجدول المنسق.

## خاتمة

وهناك لديك! باتباع هذه الخطوات، يمكنك إنشاء جدول منسق جيدًا في مستند Word باستخدام Aspose.Words for .NET. تعمل هذه المكتبة القوية على تسهيل التعامل مع مستندات Word برمجيًا، مما يوفر عليك الوقت والجهد.

## الأسئلة الشائعة

### ما هو Aspose.Words لـ .NET؟
تعد Aspose.Words for .NET مكتبة قوية لإنشاء مستندات Word وتحريرها وتحويلها برمجيًا.

### هل يمكنني استخدام ألوان مختلفة لصفوف مختلفة؟
نعم، يمكنك تطبيق تنسيقات مختلفة، بما في ذلك الألوان، على صفوف أو خلايا مختلفة.

### هل Aspose.Words لـ .NET مجاني؟
 Aspose.Words for .NET هي مكتبة مدفوعة الأجر، ولكن يمكنك الحصول على[تجربة مجانية](https://releases.aspose.com/).

### كيف يمكنني الحصول على الدعم لـ Aspose.Words لـ .NET؟
 يمكنك الحصول على الدعم من[Aspose منتديات المجتمع](https://forum.aspose.com/c/words/8).

### هل يمكنني إنشاء أنواع أخرى من المستندات باستخدام Aspose.Words لـ .NET؟
نعم، يدعم Aspose.Words for .NET تنسيقات المستندات المختلفة، بما في ذلك PDF وHTML وTXT.