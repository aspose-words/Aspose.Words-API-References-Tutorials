---
title: حدد التنسيق الشرطي
linktitle: حدد التنسيق الشرطي
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتحديد التنسيق الشرطي في جدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/programming-with-table-styles-and-formatting/define-conditional-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتحديد التنسيق الشرطي باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية تطبيق التنسيق الشرطي على جدول في مستندات Word باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ مستند Word الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد ومنشئ مستندات
 بعد ذلك ، تحتاج إلى إنشاء مثيل جديد لملف`Document` فئة ومنشئ مستند لذلك المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: ابدأ جدول جديد وأضف خلايا
لبدء إنشاء الجدول ، نستخدم ملف`StartTable()` طريقة منشئ المستندات ، ثم نضيف خلايا إلى الجدول باستخدام الامتداد`InsertCell()` الطريقة ونكتب محتويات الخلايا إلى ملف`Write()` طريقة.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## الخطوة 4: إنشاء نمط جدول وتعيين التنسيق الشرطي
 الآن يمكننا إنشاء نمط جدول باستخدام امتداد`TableStyle` الطبقة و`Add()` طريقة من الوثيقة`s `الأنماط` collection. We can then set the conditional formatting for the first row of the table by accessing the `الأنماط الشرطية` property of the table style and using the `FirstRow`.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.ConditionalStyles.FirstRow.Shading.BackgroundPatternColor = Color.GreenYellow;
tableStyle.ConditionalStyles.FirstRow.Shading.Texture = TextureIndex.TextureNone;
```

## الخطوة 5: قم بتطبيق نمط الجدول على الجدول
 أخيرًا ، نطبق نمط الجدول الذي أنشأناه على الجدول باستخدام`Style` خاصية الجدول.

```csharp
table.Style = tableStyle;
```

## الخطوة 6: احفظ المستند المعدل
أخيرًا احفظ المستند المعدل في ملف. يمكنك اختيار اسم و

  موقع مناسب لمستند الإخراج.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DefineConditionalFormatting.docx");
```

تهنئة ! لقد قمت الآن بتعريف التنسيق الشرطي لجدولك باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لـ Define Conditional Formatting باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.ConditionalStyles.FirstRow.Shading.BackgroundPatternColor = Color.GreenYellow;
	tableStyle.ConditionalStyles.FirstRow.Shading.Texture = TextureIndex.TextureNone;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DefineConditionalFormatting.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين التنسيق الشرطي باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تطبيق التنسيق الشرطي على الجداول الخاصة بك في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية الاحتياجات الخاصة.