---
title: مناطق قابلة للتحرير غير مقيدة
linktitle: مناطق قابلة للتحرير غير مقيدة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إنشاء مناطق قابلة للتحرير غير مقيدة في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/document-protection/unrestricted-editable-regions/
---

في هذا البرنامج التعليمي ، سنوجهك خلال الخطوات لاستخدام ميزة المناطق غير المقيدة القابلة للتحرير في Aspose.Words for .NET. تتيح لك هذه الميزة تحديد مناطق في مستند Word حيث يمكن تحرير المحتوى بدون قيود ، حتى إذا كان باقي المستند للقراءة فقط. اتبع الخطوات التالية:

## الخطوة 1: تحميل المستند وإعداد الحماية

ابدأ بتحميل المستند الحالي:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

حماية المستند عن طريق تعيين نوع الحماية للقراءة فقط وكلمة المرور

## الخطوة الثانية: إنشاء منطقة قابلة للتعديل

ابدأ بإنشاء منطقة قابلة للتحرير باستخدام كائنات EditableRangeStart و EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// تم إنشاء كائن EditableRange من أجل EditableRangeStart الذي قمنا به للتو.
EditableRange editableRange = edRangeStart.EditableRange;

// ضع شيئًا ما داخل النطاق القابل للتعديل.
builder.Writeln("Paragraph inside first editable range");

// يتم تشكيل النطاق القابل للتحرير بشكل جيد إذا كان له بداية ونهاية.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## الخطوة 3: أضف محتوى خارج المناطق القابلة للتعديل

يمكنك إضافة محتوى خارج المناطق القابلة للتحرير ، والتي ستبقى للقراءة فقط:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## الخطوة 4: احفظ المستند

أخيرًا ، احفظ المستند المعدل:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

تأكد من تحديد المسار الصحيح واسم الملف لحفظ المستند بالمناطق القابلة للتحرير.

### مثال على شفرة المصدر للمناطق غير المقيدة القابلة للتحرير باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للمناطق القابلة للتحرير غير المقيدة باستخدام Aspose.Words for .NET:

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// تحميل مستند وجعله للقراءة فقط.
	Document doc = new Document(MyDir + "Document.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	doc.Protect(ProtectionType.ReadOnly, "MyPassword");

	builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

	// ابدأ نطاقًا قابلًا للتحرير.
	EditableRangeStart edRangeStart = builder.StartEditableRange();
	// تم إنشاء كائن EditableRange من أجل EditableRangeStart الذي قمنا به للتو.
	EditableRange editableRange = edRangeStart.EditableRange;

	// ضع شيئًا ما داخل النطاق القابل للتعديل.
	builder.Writeln("Paragraph inside first editable range");

	// يتم تشكيل النطاق القابل للتحرير بشكل جيد إذا كان له بداية ونهاية.
	EditableRangeEnd edRangeEnd = builder.EndEditableRange();

	builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

	doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
باتباع هذه الخطوات ، يمكنك بسهولة إنشاء مناطق قابلة للتحرير غير مقيدة في مستند Word الخاص بك باستخدام Aspose.Words for .NET.


