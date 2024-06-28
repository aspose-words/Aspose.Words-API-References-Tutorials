---
title: التخطيط في الخلية
linktitle: التخطيط في الخلية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تخطيط شكل داخل خلية جدول في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/layout-in-cell/
---

يشرح هذا البرنامج التعليمي كيفية تخطيط شكل داخل خلية جدول في مستند Word باستخدام Aspose.Words لـ .NET. من خلال ضبط خصائص الشكل واستخدام خيارات التخطيط، يمكنك التحكم في موضع الشكل ومظهره داخل الخلية.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي، يجب أن يكون لديك ما يلي:

- تم تثبيت Aspose.Words لمكتبة .NET.
- المعرفة الأساسية بـ C# ومعالجة الكلمات باستخدام مستندات Word.

## الخطوة 1: إعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى الدليل الذي تريد حفظ المستند فيه.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد وDocumentBuilder
 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` كائن للعمل مع الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: بناء الجدول
 استخدم ال`StartTable`, `EndTable`, `InsertCell` ، و`Write` أساليب`DocumentBuilder`كائن لبناء جدول. قم بتعيين ارتفاع الصف المطلوب وقاعدة الارتفاع باستخدام`RowFormat` ملكيات.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## الخطوة 4: إنشاء وتنسيق الشكل
 إنشاء`Shape` الكائن وتكوين خصائصه لتحديد العلامة المائية. قم بتعيين الشكل الذي سيتم وضعه داخل الخلية باستخدام`IsLayoutInCell` ملكية.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true,
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## الخطوة 5: تخصيص الشكل
 قم بتخصيص مظهر ونص شكل العلامة المائية عن طريق تعيين خصائص مثل`FillColor`, `StrokeColor`, `TextPath`, `Name`, `WrapType`، إلخ.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## الخطوة 6: أدخل الشكل في المستند
 أدخل شكل العلامة المائية في المستند باستخدام`InsertNode` طريقة`DocumentBuilder` هدف. ضع الشكل باستخدام`MoveTo` طريقة لوضعه بعد آخر تشغيل في المستند.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## الخطوة 7: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save` طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithShapes.LayoutInCell.docx".

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
doc

.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

### مثال على التعليمات البرمجية المصدر للتخطيط في الخلية باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.RowFormat.Height = 100;
	builder.RowFormat.HeightRule = HeightRule.Exactly;
	for (int i = 0; i < 31; i++)
	{
		if (i != 0 && i % 7 == 0) builder.EndRow();
		builder.InsertCell();
		builder.Write("Cell contents");
	}
	builder.EndTable();
	Shape watermark = new Shape(doc, ShapeType.TextPlainText)
	{
		RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
		RelativeVerticalPosition = RelativeVerticalPosition.Page,
		IsLayoutInCell = true, // عرض الشكل خارج خلية الجدول إذا كان سيتم وضعه في خلية.
		Width = 300,
		Height = 70,
		HorizontalAlignment = HorizontalAlignment.Center,
		VerticalAlignment = VerticalAlignment.Center,
		Rotation = -40
	};
	watermark.FillColor = Color.Gray;
	watermark.StrokeColor = Color.Gray;
	watermark.TextPath.Text = "watermarkText";
	watermark.TextPath.FontFamily = "Arial";
	watermark.Name = $"WaterMark_{Guid.NewGuid()}";
	watermark.WrapType = WrapType.None;
	Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
	builder.MoveTo(run);
	builder.InsertNode(watermark);
	doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
	doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

هذا كل شيء! لقد نجحت في تخطيط شكل داخل خلية جدول في مستند Word باستخدام Aspose.Words لـ .NET.