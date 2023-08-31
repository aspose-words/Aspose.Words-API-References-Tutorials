---
title: احصل على أنواع المراجعة للكلمات
linktitle: احصل على أنواع المراجعة للكلمات
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: احصل على مراجعة أنواع الكلمات في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/get-revision-types/
---

في هذا الدليل التدريجي ، سنخبرك بكيفية الحصول على أنواع تنقيحات الكلمات في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة الثانية: تصفح الفقرات

بعد ذلك ، سنتصفح فقرات المستند ونتحقق من أنواع تنقيحات الكلمات المرتبطة بكل فقرة.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     if (paragraphs[i].IsMoveFromRevision)
         Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
     if (paragraphs[i].IsMoveToRevision)
         Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

### مثال على شفرة المصدر للحصول على أنواع المراجعة باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للحصول على أنواع المراجعة في مستند باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
	 if (paragraphs[i].IsMoveFromRevision)
		 Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
	 if (paragraphs[i].IsMoveToRevision)
		 Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية الحصول على أنواع مراجعات الكلمات في مستند Word باستخدام Aspose.Words for .NET. لقد اتبعنا الخطوات لتحميل المستند ، وتصفح الفقرات ، والتحقق من أنواع مراجعات الكلمات المرتبطة بكل فقرة. يمكنك الآن تطبيق هذه المعرفة لتحليل مراجعات الكلمات في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة للحصول على أنواع مراجعة الكلمات

#### س: كيف يمكن تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم ملف`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكنني تكرار الفقرات في مستند في Aspose.Words for .NET؟

 ج: استخدم ملف`Paragraphs` خاصية قسم الوثيقة للحصول على مجموعة من الفقرات. يمكنك بعد ذلك استخدام حلقة للتكرار خلال كل فقرة.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // قم بمعالجة كل فقرة هنا
}
```

#### س: كيف تتحقق مما إذا تم نقل فقرة (حذفها) في Aspose.Words for .NET؟

 ج: استخدم فقرة`IsMoveFromRevision` للتحقق مما إذا كان قد تم نقله (محذوف).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // تم نقل الفقرة (حذف)
}
```

#### س: كيف تتحقق مما إذا تم نقل فقرة (إدخالها) في Aspose.Words for .NET؟

 ج: استخدم فقرة`IsMoveToRevision`للتحقق مما إذا كان قد تم نقله (مدرج).

```csharp
if (paragraph.IsMoveToRevision)
{
     // تم نقل الفقرة (إدراجها)
}
```