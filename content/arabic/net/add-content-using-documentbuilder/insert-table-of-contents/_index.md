---
title: إدراج جدول المحتويات في مستند Word
linktitle: إدراج جدول المحتويات في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إدراج جدول محتويات في Word باستخدام Aspose.Words لـ .NET. اتبع دليلنا خطوة بخطوة للتنقل السلس بين المستندات.
type: docs
weight: 10
url: /ar/net/add-content-using-documentbuilder/insert-table-of-contents/
---
## مقدمة
ستتعلم في هذا البرنامج التعليمي كيفية إضافة جدول محتويات (TOC) بكفاءة إلى مستندات Word الخاصة بك باستخدام Aspose.Words for .NET. تعد هذه الميزة ضرورية لتنظيم المستندات الطويلة والتنقل فيها، وتحسين إمكانية القراءة، وتقديم نظرة عامة سريعة على أقسام المستند.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

- الفهم الأساسي لـ C# و.NET Framework.
- تم تثبيت Visual Studio على جهازك.
-  Aspose.Words لمكتبة .NET. إذا لم تكن قد قمت بتثبيته بعد، يمكنك تنزيله من[هنا](https://releases.aspose.com/words/net/).

## استيراد مساحات الأسماء

للبدء، قم باستيراد مساحات الأسماء الضرورية في مشروع C# الخاص بك:

```csharp
using Aspose.Words;
using Aspose.Words.Builder;
using Aspose.Words.Fields;
using Aspose.Words.Tables;
```

دعونا نقسم العملية إلى خطوات واضحة:

## الخطوة 1: تهيئة مستند Aspose.Words وDocumentBuilder

 أولاً، قم بتهيئة Aspose.Words جديد`Document` كائن و`DocumentBuilder` للعمل مع:

```csharp
// تهيئة المستند و DocumentBuilder
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 2: أدخل جدول المحتويات

 الآن، قم بإدراج جدول المحتويات باستخدام`InsertTableOfContents` طريقة:

```csharp
// إدراج جدول المحتويات
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## الخطوة 3: ابدأ محتوى المستند على صفحة جديدة

لضمان التنسيق الصحيح، ابدأ محتوى المستند الفعلي في صفحة جديدة:

```csharp
// إدراج فاصل الصفحات
builder.InsertBreak(BreakType.PageBreak);
```

## الخطوة 4: هيكلة المستند الخاص بك مع العناوين

قم بتنظيم محتوى المستند باستخدام أنماط العناوين المناسبة:

```csharp
// ضبط أنماط العناوين
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

## الخطوة 5: تحديث وملء جدول المحتويات

قم بتحديث جدول المحتويات ليعكس بنية الوثيقة:

```csharp
// قم بتحديث حقول جدول المحتويات
doc.UpdateFields();
```

## الخطوة 6: احفظ المستند

وأخيرًا، احفظ مستندك في دليل محدد:

```csharp
// احفظ المستند
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
doc.Save(dataDir + "InsertTableOfContentsUsingAsposeWords.docx");
```

## خاتمة

تعد إضافة جدول محتويات باستخدام Aspose.Words for .NET أمرًا مباشرًا وتعزز سهولة استخدام مستنداتك بشكل كبير. باتباع هذه الخطوات، يمكنك تنظيم المستندات المعقدة والتنقل خلالها بكفاءة.

## الأسئلة الشائعة

### هل يمكنني تخصيص مظهر جدول المحتويات؟
نعم، يمكنك تخصيص مظهر وسلوك جدول المحتويات باستخدام Aspose.Words لواجهات برمجة تطبيقات .NET.

### هل يدعم Aspose.Words تحديث الحقول تلقائيًا؟
نعم، يتيح لك Aspose.Words تحديث الحقول مثل جدول المحتويات ديناميكيًا بناءً على تغييرات المستند.

### هل يمكنني إنشاء جداول محتويات متعددة في مستند واحد؟
يدعم Aspose.Words إنشاء جداول محتويات متعددة بإعدادات مختلفة داخل مستند واحد.

### هل Aspose.Words متوافق مع الإصدارات المختلفة من Microsoft Word؟
نعم، يضمن Aspose.Words التوافق مع الإصدارات المختلفة من تنسيقات Microsoft Word.

### أين يمكنني العثور على مزيد من المساعدة والدعم لـ Aspose.Words؟
لمزيد من المساعدة، قم بزيارة[Aspose.منتدى الكلمات](https://forum.aspose.com/c/words/8) أو تحقق من[الوثائق الرسمية](https://reference.aspose.com/words/net/).