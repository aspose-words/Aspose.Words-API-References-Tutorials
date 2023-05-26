---
title: مرساة عمودية
linktitle: مرساة عمودية
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية وضع الشكل عموديًا داخل مستند باستخدام ميزة الارتساء العمودي في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/vertical-anchor/
---

يشرح هذا البرنامج التعليمي كيفية استخدام ميزة الارتساء العمودي في Aspose.Words for .NET لوضع الشكل عموديًا داخل المستند. من خلال تعيين خاصية الارتساء العمودي للشكل ، يمكنك التحكم في المحاذاة الرأسية بالنسبة إلى النص أو الصفحة.

## المتطلبات الأساسية
لمتابعة هذا البرنامج التعليمي ، يجب أن يكون لديك ما يلي:

- تثبيت Aspose.Words لمكتبة .NET.
- معرفة أساسية بـ C # والعمل مع مستندات Word.

## الخطوة 1: قم بإعداد دليل المستندات
 ابدأ بإعداد المسار إلى دليل المستندات الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"`بالمسار الفعلي للدليل حيث تريد حفظ المستند.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند جديد و DocumentBuilder
 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` كائن للعمل مع المستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: إدراج وتكوين شكل
 أدخل شكلاً في المستند باستخدام ملف`InsertShape` طريقة`DocumentBuilder` هدف. اضبط الأبعاد المطلوبة للشكل.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## الخطوة 4: اضبط المرساة الرأسية
قم بتعيين خاصية الارتساء العمودي للشكل للتحكم في المحاذاة الرأسية. في هذا المثال ، قمنا بتعيينه على "الجزء السفلي" لربط الشكل أسفل النص أو الصفحة.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## الخطوة 5: أضف محتوى إلى الشكل
 استخدم ال`MoveTo` طريقة`DocumentBuilder` كائن لتحريك المؤشر إلى الفقرة الأولى من الشكل. ثم استخدم ملف`Write` طريقة لإضافة محتوى إلى الشكل.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة. قم بتوفير اسم الملف المطلوب بامتداد الملف المناسب. في هذا المثال ، نحفظ المستند باسم "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### مثال على شفرة المصدر لـ Vertical Anchor باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

هذا كل شيء! لقد نجحت في استخدام ميزة الارتساء العمودي في Aspose.Words for .NET لوضع الشكل عموديًا داخل المستند.