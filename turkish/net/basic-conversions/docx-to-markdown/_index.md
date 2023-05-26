---
title: Docx إلى Markdown
linktitle: Docx إلى Markdown
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحويل مستندات Word من Docx إلى تنسيق Markdown باستخدام Aspose.Words for .NET. برنامج تعليمي خطوة بخطوة مع مثال على الكود المصدري.
type: docs
weight: 10
url: /tr/net/basic-conversions/docx-to-markdown/
---

في هذا البرنامج التعليمي خطوة بخطوة ، سنوجهك حول كيفية استخدام Aspose.Words for .NET لتحويل مستند Word بتنسيق Docx إلى Markdown. سنشرح كود المصدر C # المقدم ونوضح لك كيفية تنفيذه في مشاريعك الخاصة.

للبدء ، تأكد من تثبيت وإعداد Aspose.Words for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك ، فقم بتنزيل المكتبة وتثبيتها من الموقع الرسمي.

## الخطوة 1: تهيئة المستند وكائنات DocumentBuilder

 أولاً ، قم بتهيئة ملف`Document` الكائن و`DocumentBuilder` هدف:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة الثانية: إضافة محتوى إلى المستند

 بعد ذلك ، استخدم ملف`DocumentBuilder` كائن لإضافة محتوى إلى المستند. في هذا المثال ، سنضيف فقرة نصية بسيطة باستخدام امتداد`Writeln` طريقة:

```csharp
builder.Writeln("Some text!");
```

لا تتردد في إضافة محتوى أكثر تعقيدًا مثل العناوين أو الجداول أو القوائم أو التنسيق حسب الحاجة.

## الخطوة 3: حفظ المستند بتنسيق Markdown

 لحفظ المستند بتنسيق Markdown ، استخدم ملف`Save` طريقة على`Document` كائن وتوفير المسار واسم الملف للمستند الناتج. في هذا المثال ، سنحفظه باسم`"BaseConversions.DocxToMarkdown.md"`:

```csharp
doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");
```

هذا كل شيء! لقد نجحت في تحويل مستند Word بتنسيق Docx إلى Markdown باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Docx To Markdown باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Some text!");

	doc.Save(dataDir + "BaseConversions.DocxToMarkdown.md");

```

لا تتردد في استخدام هذا الرمز في مشاريعك الخاصة وتعديله وفقًا لمتطلباتك الخاصة.