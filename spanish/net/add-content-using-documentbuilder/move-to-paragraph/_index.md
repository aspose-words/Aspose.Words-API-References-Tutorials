---
title: الانتقال إلى الفقرة
linktitle: الانتقال إلى الفقرة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام ميزة Aspose.Words for .NET's Move To Paragraph للتنقل ومعالجة الفقرات في مستندات Word برمجيًا.
type: docs
weight: 10
url: /es/net/add-content-using-documentbuilder/move-to-paragraph/
---

في هذا المثال خطوة بخطوة ، سوف نستكشف ميزة Move To Paragraph في Aspose.Words for .NET. تسمح هذه الميزة للمطورين بالتنقل ومعالجة الفقرات داخل مستند Word برمجيًا. باتباع هذا الدليل ، ستتعلم كيفية تنفيذ ميزة الانتقال إلى الفقرة واستخدامها بشكل فعال.

يوضح الكود أعلاه استخدام ميزة Move To Paragraph. دعونا نفهم كل خطوة بالتفصيل:

## الخطوة 1: تحميل المستند

 نبدأ بتحميل مستند Word في مثيل`Document` فصل. ال`MyDir`متغير يمثل مسار الدليل حيث يوجد المستند. يجب استبداله بمسار الدليل الفعلي أو تعديل الكود وفقًا لذلك.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");
```

## الخطوة 2: تهيئة DocumentBuilder

 بعد ذلك ، نقوم بإنشاء ملف`DocumentBuilder` الكائن وربطه بالمستند الذي تم تحميله. ال`DocumentBuilder` توفر class طرقًا وخصائص مختلفة لمعالجة محتوى المستند.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: الانتقال إلى فقرة محددة

 ال`MoveToParagraph` يتم استخدام الطريقة لوضع منشئ المستند في فقرة معينة داخل المستند. يأخذ معلمتين: فهرس الفقرة الهدف وموضع الحرف داخل تلك الفقرة (يمثل 0 بداية الفقرة).

في المثال المقدم ، ننتقل إلى الفقرة الثالثة (الفهرس 2) من المستند:

```csharp
builder.MoveToParagraph(2, 0);
```

## الخطوة 4: تعديل محتوى الفقرة

 بمجرد وضع المنشئ في الفقرة المطلوبة ، يمكننا استخدام الامتداد`Writeln`طريقة لإضافة أو تعديل محتوى تلك الفقرة. في هذه الحالة ، نضيف النص "هذه هي الفقرة الثالثة".

```csharp
builder.Writeln("This is the 3rd paragraph.");
```

### مثال كود المصدر للانتقال إلى الفقرة باستخدام Aspose.Words for .NET

فيما يلي المثال الكامل لشفرة المصدر لتنفيذ ميزة Move To Paragraph باستخدام Aspose.Words for .NET:

```csharp

	Document doc = new Document(MyDir + "Paragraphs.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToParagraph(2, 0);
	builder.Writeln("This is the 3rd paragraph.");
	
```

باتباع هذا الدليل واستخدام ميزة النقل إلى الفقرة ، يمكنك معالجة الفقرات برمجيًا في مستندات Word باستخدام Aspose.Words for .NET.

