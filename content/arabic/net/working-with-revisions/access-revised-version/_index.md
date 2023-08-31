---
title: الوصول إلى النسخة المنقحة
linktitle: الوصول إلى النسخة المنقحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: الوصول إلى نسخة منقحة من مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/access-revised-version/
---

في هذا الدليل خطوة بخطوة، سنوضح لك كيفية الوصول إلى الإصدار المنقح من مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق مخرجات تخفيض السعر.

## الخطوة 1: تحميل الوثيقة

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## الخطوة 2: الوصول إلى النسخة المعدلة

سننتقل الآن إلى النسخة المنقحة من الوثيقة.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## الخطوة 3: تصفح المراجعات

بعد ذلك، سنقوم بمراجعة المراجعات الموجودة في المستند وعرض معلومات محددة للفقرات التي تمثل عناصر القائمة.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### مثال على التعليمات البرمجية المصدر للوصول إلى الإصدار المنقح باستخدام Aspose.Words لـ .NET

فيما يلي الكود المصدري الكامل للوصول إلى النسخة المنقحة من المستند باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// قم بالتبديل إلى الإصدار المنقح من المستند.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية الوصول إلى النسخة المعدلة من مستند Word باستخدام Aspose.Words لـ .NET. ومن خلال تحميل المستند، والانتقال إلى النسخة المنقحة، وتصفح المراجعات، تمكنا من الحصول على معلومات محددة للفقرات التي تمثل عناصر القائمة. يوفر Aspose.Words for .NET ميزات قوية لمعالجة مستندات Word، بما في ذلك الوصول إلى المراجعات. يمكنك الآن استخدام هذه المعرفة للوصول إلى الإصدار المنقح من مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### الأسئلة الشائعة

#### س: كيف يمكنني تحميل مستند يحتوي على مراجعات إلى Aspose.Words لـ .NET؟

 ج: استخدم`Document`فئة Aspose.Words لـ .NET لتحميل مستند من ملف يحتوي على مراجعات. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكنني الوصول إلى النسخة المعدلة من المستند في Aspose.Words لـ .NET؟

 ج: استخدم`RevisionsView` ملكية`Document` كائن للوصول إلى النسخة المنقحة من الوثيقة. يمكنك ضبط قيمة`RevisionsView` الملكية ل`RevisionsView.Final` لإظهار النسخة النهائية بدون المراجعات.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### س: كيف يمكنني استعراض مراجعات المستندات في Aspose.Words لـ .NET؟

 ج: استخدم أ`foreach` حلقة للتكرار من خلال المراجعات الموجودة في المستند. يمكنك استخدام ال`Revisions` ملكية`Document` كائن للحصول على مجموعة من كافة مراجعات المستند.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // معالجة كل مراجعة هنا
}
```

#### س: كيف يمكن التحقق مما إذا كانت الفقرة عبارة عن عنصر قائمة في Aspose.Words لـ .NET؟

 ج: استخدم`IsListItem` ملكية`Paragraph` كائن للتحقق مما إذا كانت الفقرة عنصر قائمة. ال`IsListItem` عوائد الممتلكات`true` إذا كانت الفقرة عبارة عن عنصر قائمة، وإلا فسيتم إرجاعها`false`.

```csharp
if (paragraph.IsListItem)
{
     // الفقرة عبارة عن عنصر قائمة
}
else
{
     // الفقرة ليست عنصر قائمة
}
```