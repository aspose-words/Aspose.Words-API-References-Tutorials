---
title: الحصول على أنواع المراجعة من الكلمات
linktitle: الحصول على أنواع المراجعة من الكلمات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: احصل على أنواع مراجعة الكلمات في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/get-revision-types/
---

في هذا الدليل خطوة بخطوة، سنخبرك بكيفية الحصول على أنواع مراجعات الكلمات في مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق مخرجات تخفيض السعر.

## الخطوة 1: تحميل الوثيقة

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
```

## الخطوة 2: انتقل من خلال الفقرات

بعد ذلك، سنستعرض فقرات المستند ونتحقق من أنواع مراجعات الكلمات المرتبطة بكل فقرة.

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

### مثال على التعليمات البرمجية المصدر للحصول على أنواع المراجعة باستخدام Aspose.Words لـ .NET

فيما يلي كود المصدر الكامل للحصول على أنواع المراجعة في مستند باستخدام Aspose.Words for .NET:

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

في هذا البرنامج التعليمي، تعلمنا كيفية الحصول على أنواع مراجعات الكلمات في مستند Word باستخدام Aspose.Words for .NET. لقد اتبعنا خطوات تحميل المستند وتصفح الفقرات والتحقق من أنواع مراجعات الكلمات المرتبطة بكل فقرة. يمكنك الآن تطبيق هذه المعرفة لتحليل مراجعات الكلمات في مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة للحصول على أنواع المراجعة للكلمات

#### س: كيفية تحميل مستند في Aspose.Words لـ .NET؟

 ج: استخدم`Document` فئة Aspose.Words لـ .NET لتحميل مستند من ملف. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكنني تكرار الفقرات في مستند في Aspose.Words لـ .NET؟

 ج: استخدم`Paragraphs` خاصية قسم الوثيقة للحصول على مجموعة الفقرات. يمكنك بعد ذلك استخدام حلقة للتكرار خلال كل فقرة.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
for (int i = 0; i < paragraphs.Count; i++)
{
     // معالجة كل فقرة هنا
}
```

#### س: كيف يمكن التحقق من نقل فقرة (حذفها) في Aspose.Words لـ .NET؟

 ج: استخدم فقرة`IsMoveFromRevision`الخاصية للتحقق مما إذا تم نقلها (حذفها).

```csharp
if (paragraph. IsMove

FromRevision)
{
     // تم نقل الفقرة (محذوفة)
}
```

#### س: كيف يمكن التحقق من نقل فقرة (إدراجها) في Aspose.Words لـ .NET؟

 ج: استخدم فقرة`IsMoveToRevision` الخاصية للتحقق مما إذا تم نقلها (إدراجها).

```csharp
if (paragraph.IsMoveToRevision)
{
     // تم نقل الفقرة (إدراجها)
}
```