---
title: الوصول إلى النسخة المنقحة
linktitle: الوصول إلى النسخة المنقحة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: قم بالوصول إلى نسخة منقحة من مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-revisions/access-revised-version/
---

في هذا الدليل المفصل خطوة بخطوة ، سوف نوضح لك كيفية الوصول إلى النسخة المنقحة من مستند Word باستخدام Aspose.Words for .NET. سنزودك بكود المصدر الكامل ونوضح لك كيفية تنسيق إخراج تخفيض السعر.

## الخطوة 1: تحميل المستند

الخطوة الأولى هي تحميل المستند الذي يحتوي على المراجعات.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## الخطوة 2: الوصول إلى النسخة المعدلة

ننتقل الآن إلى النسخة المنقحة من الوثيقة.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## الخطوة 3: تصفح المراجعات

بعد ذلك ، سنقوم بتكرار المراجعات الموجودة في المستند ونعرض معلومات محددة للفقرات التي هي عناصر قائمة.

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

### مثال على شفرة المصدر لـ Access Revised Version باستخدام Aspose.Words for .NET

فيما يلي رمز المصدر الكامل للوصول إلى النسخة المعدلة من المستند باستخدام Aspose.Words for .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// قم بالتبديل إلى النسخة المنقحة من المستند.
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

في هذا البرنامج التعليمي ، تعلمنا كيفية الوصول إلى النسخة المنقحة من مستند Word باستخدام Aspose.Words for .NET. من خلال تحميل المستند ، والانتقال إلى النسخة المنقحة ، وتصفح المراجعات ، تمكنا من الحصول على معلومات محددة للفقرات التي هي عناصر قائمة. يوفر Aspose.Words for .NET ميزات قوية لمعالجة مستندات Word ، بما في ذلك الوصول إلى المراجعات. يمكنك الآن استخدام هذه المعرفة للوصول إلى النسخة المنقحة من مستندات Word الخاصة بك باستخدام Aspose.Words for .NET.

### التعليمات

#### س: كيف يمكنني تحميل مستند يحتوي على مراجعات في Aspose.Words for .NET؟

 ج: استخدم ملف`Document`فئة Aspose.Words for .NET لتحميل مستند من ملف يحتوي على مراجعات. يمكنك تحديد مسار المستند بالكامل.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### س: كيف يمكنني الوصول إلى النسخة المنقحة من المستند في Aspose.Words for .NET؟

 ج: استخدم ملف`RevisionsView`ممتلكات`Document` على الوصول إلى النسخة المنقحة من المستند. يمكنك تعيين قيمة ملف`RevisionsView` ملكية ل`RevisionsView.Final` لإظهار النسخة النهائية بدون المراجعات.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### س: كيف أتصفح تنقيحات المستندات في Aspose.Words لـ .NET؟

 ج: استخدم أ`foreach` حلقة للتكرار خلال المراجعات الموجودة في المستند. يمكنك استخدام ال`Revisions`ممتلكات`Document` للحصول على مجموعة من كافة المراجعات للمستند.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // معالجة كل مراجعة هنا
}
```

#### س: كيف تتحقق مما إذا كانت الفقرة هي عنصر قائمة في Aspose.Words for .NET؟

 ج: استخدم ملف`IsListItem`ممتلكات`Paragraph` للتحقق مما إذا كانت الفقرة عبارة عن عنصر قائمة. ال`IsListItem` إرجاع الممتلكات`true` إذا كانت الفقرة عنصر قائمة ، وإلا فإنها ستعود`false`.

```csharp
if (paragraph.IsListItem)
{
     // الفقرة عنصر قائمة
}
else
{
     // الفقرة ليست عنصر قائمة
}
```