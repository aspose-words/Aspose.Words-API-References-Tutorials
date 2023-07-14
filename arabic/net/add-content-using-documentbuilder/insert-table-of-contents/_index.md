---
title: أدخل جدول المحتويات
linktitle: أدخل جدول المحتويات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج جدول محتويات في مستندات Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-table-of-contents/
---

في هذا البرنامج التعليمي الشامل ، ستتعلم كيفية إدراج جدول محتويات في مستند Word باستخدام Aspose.Words for .NET. سنوجهك خلال العملية ونزودك بمقتطفات كود C # الضرورية. بنهاية هذا الدليل ، ستتمكن من إنشاء جدول محتويات بالعناوين المناسبة وأرقام الصفحات.

## المتطلبات الأساسية
قبل أن نبدأ ، تأكد من توفر المتطلبات الأساسية التالية لديك:
- تم تثبيت Aspose.Words for .NET library على نظامك.

## الخطوة 1: إنشاء مستند جديد و DocumentBuilder
للبدء ، قم بإنشاء مستند جديد باستخدام فئة المستند وتهيئة كائن DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل جدول المحتويات
بعد ذلك ، استخدم الأسلوب InsertTableOfContents لفئة DocumentBuilder لإدراج جدول محتويات. حدد خيارات التنسيق المطلوبة في الطريقة:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## الخطوة 3: إضافة محتوى المستند
بعد إدراج جدول المحتويات ، أضف محتوى المستند الفعلي. قم بتعيين أنماط العناوين المناسبة باستخدام StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## الخطوة 4: تحديث جدول المحتويات
سيكون جدول المحتويات المُدرج حديثًا فارغًا في البداية. لتعبئتها ، قم بتحديث الحقول في المستند:

```csharp
doc.UpdateFields();
```

## الخطوة 5: احفظ المستند
بعد إدراج جدول المحتويات وتحديث الحقول ، احفظ المستند في ملف باستخدام طريقة Save من فئة Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### مثال كود المصدر لإدراج جدول المحتويات باستخدام Aspose.Words for .NET
فيما يلي الكود المصدري الكامل لإدخال جدول محتويات باستخدام Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// تهيئة DocumentBuilder بكائن المستند
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج جدول المحتويات
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// ابدأ محتوى المستند الفعلي في الصفحة الثانية.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// سيكون جدول المحتويات المُدرج حديثًا فارغًا في البداية.
// يجب أن يتم ملؤها عن طريق تحديث الحقول في المستند.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```
