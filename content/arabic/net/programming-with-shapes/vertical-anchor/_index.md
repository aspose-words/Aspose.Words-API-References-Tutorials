---
title: مرساة عمودية
linktitle: مرساة عمودية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية وضع الشكل عموديًا داخل المستند باستخدام ميزة الارتساء الرأسي في Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-shapes/vertical-anchor/
---

يشرح هذا البرنامج التعليمي كيفية استخدام ميزة الارتساء الرأسي في Aspose.Words لـ .NET لوضع شكل عموديًا داخل المستند. من خلال تعيين خاصية الارتساء الرأسي للشكل، يمكنك التحكم في محاذاته الرأسية بالنسبة للنص أو الصفحة.

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

## الخطوة 3: إدراج شكل وتكوينه
 قم بإدراج شكل في المستند باستخدام`InsertShape` طريقة`DocumentBuilder` هدف. ضبط الأبعاد المطلوبة للشكل.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## الخطوة 4: تعيين المرساة العمودية
قم بتعيين خاصية الإرساء الرأسي للشكل للتحكم في محاذاته الرأسية. في هذا المثال، قمنا بتعيينه على "أسفل" لتثبيت الشكل أسفل النص أو الصفحة.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## الخطوة 5: إضافة محتوى إلى الشكل
 استخدم ال`MoveTo` طريقة`DocumentBuilder` كائن لتحريك المؤشر إلى الفقرة الأولى من الشكل. ثم استخدم`Write` طريقة إضافة المحتوى إلى الشكل.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## الخطوة 6: احفظ المستند
 احفظ المستند في الدليل المحدد باستخدام ملف`Save`طريقة. قم بتوفير اسم الملف المطلوب مع امتداد الملف المناسب. في هذا المثال، نقوم بحفظ المستند باسم "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### مثال على التعليمات البرمجية المصدر لـ Vertical Anchor باستخدام Aspose.Words لـ .NET 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

هذا كل شيء! لقد نجحت في استخدام ميزة الارتساء الرأسي في Aspose.Words لـ .NET لوضع شكل عموديًا داخل المستند.