---
title: إنشاء نمط الجدول
linktitle: إنشاء نمط الجدول
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإنشاء نمط جدول مخصص باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-table-styles-and-formatting/create-table-style/
---

في هذا البرنامج التعليمي، سنرشدك خلال العملية خطوة بخطوة لإنشاء نمط جدول باستخدام Aspose.Words for .NET. سنشرح لك التعليمات البرمجية المصدرية المجمعة لـ C# ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي، ستعرف كيفية إنشاء نمط مخصص لجداولك في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو الموقع الذي تريد حفظ مستند Word الذي تم تحريره فيه. استبدل "دليل المستندات الخاصة بك" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد ومنشئ المستندات
 بعد ذلك، تحتاج إلى إنشاء مثيل جديد لـ`Document` فئة ومنشئ مستند لتلك الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: ابدأ جدولاً جديدًا وأضف الخلايا
للبدء في إنشاء الجدول، نستخدم`StartTable()` طريقة منشئ المستندات، ثم نضيف خلايا إلى الجدول باستخدام`InsertCell()` الطريقة ونكتب محتويات الخلايا باستخدام`Write()` طريقة.

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

## الخطوة 4: إنشاء نمط الجدول
 الآن يمكننا إنشاء نمط الجدول باستخدام`TableStyle` الطبقة و`Add()` الطريقة من الوثيقة`s `مجموعة الأنماط. نقوم بتعريف خصائص النمط، مثل الحدود والهوامش والحشوات.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## الخطوة 5: تطبيق نمط الجدول على الجدول
 وأخيرًا، نقوم بتطبيق نمط الجدول الذي أنشأناه على الجدول باستخدام ملف`Style` خاصية الجدول.

```csharp
table.Style = tableStyle;
```

## الخطوة 6: احفظ المستند المعدل
أخيرًا احفظ المستند المعدل في ملف. يمكنك اختيار الاسم والموقع المناسبين للمستند الناتج.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

تهنئة ! لقد قمت الآن بإنشاء نمط مخصص لجدولك باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لإنشاء نمط الجدول باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
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
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## خاتمة
في هذا البرنامج التعليمي، تعلمنا كيفية إنشاء نمط جدول باستخدام Aspose.Words لـ .NET. باتباع هذا الدليل المفصّل خطوة بخطوة، يمكنك بسهولة تخصيص نمط جداولك في مستندات Word. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة، يمكنك تحسين العرض المرئي لمستندات Word الخاصة بك وتلبية الاحتياجات المحددة.