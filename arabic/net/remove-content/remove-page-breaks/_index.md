---
title: إزالة فواصل الصفحات
linktitle: إزالة فواصل الصفحات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إزالة فواصل الصفحات في مستند باستخدام Aspose.Words Library for .NET. اتبع دليلنا المفصل خطوة بخطوة للحصول على تخطيط سلس.
type: docs
weight: 10
url: /ar/net/remove-content/remove-page-breaks/
---
في هذا البرنامج التعليمي ، سوف نستكشف كيفية إزالة فواصل الصفحات من مستند باستخدام مكتبة Aspose.Words for .NET. يمكن أن تتداخل فواصل الصفحات أحيانًا مع تنسيق المستند وتخطيطه ، وقد يكون من الضروري إزالتهما برمجيًا. سنقدم دليلاً خطوة بخطوة لمساعدتك على فهم العملية وتنفيذها في مشاريع C # الخاصة بك.

## متطلبات

قبل أن نبدأ ، تأكد من توفر لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C #
- تثبيت Aspose.Words لمكتبة .NET
- Visual Studio أو أي بيئة تطوير أخرى لـ C # تم إعدادها

## الخطوة الأولى: تهيئة البيئة

للبدء ، قم بإنشاء مشروع C # جديد في بيئة التطوير المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET بشكل صحيح في مشروعك.

## الخطوة الثانية: تحميل المستند

لإزالة فواصل الصفحات من المستند ، نحتاج أولاً إلى تحميل المستند في الذاكرة. يوضح الكود التالي كيفية تحميل مستند من دليل معين:

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

//قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى المستند الخاص بك.

## الخطوة 3: إزالة فواصل الصفحات

بمجرد تحميل المستند ، يمكننا البدء في إزالة فواصل الصفحات. يوضح مقتطف الشفرة أدناه كيفية تكرار جميع الفقرات في المستند والتحقق من فواصل الصفحات وإزالتها:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
     // إذا كانت الفقرة تحتوي على فاصل صفحات من قبل ، فقم بمسحها
     if (para.ParagraphFormat.PageBreakBefore)
         para.ParagraphFormat.PageBreakBefore = false;

     // تحقق من كل عمليات التشغيل في الفقرة بحثًا عن فواصل الصفحات وقم بإزالتها
     foreach(Run run in para.Runs)
     {
         if (run.Text.Contains(ControlChar.PageBreak))
             run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
     }
}
```

يتكرر مقتطف الشفرة أعلاه عبر جميع الفقرات في المستند ويتحقق مما إذا كانت كل فقرة بها فاصل صفحات قبلها. إذا تم الكشف عن فاصل صفحة ، يتم مسحه. بعد ذلك ، يتحقق من كل تشغيل داخل الفقرة بحثًا عن فواصل الصفحات ويزيلها.

## الخطوة 4: حفظ المستند المعدل

بعد إزالة فواصل الصفحات ، نحتاج إلى حفظ المستند المعدل. يوضح الكود التالي كيفية حفظ المستند المعدل في موقع معين:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 يستبدل`"modified-document.docx"` بالاسم الذي تريده للمستند المعدل.

### نموذج شفرة مصدر لإزالة فواصل الصفحات باستخدام Aspose.Words for .NET 
```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
//قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");

NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
	// إذا كانت الفقرة تحتوي على فاصل صفحات قبل المجموعة ، فقم بمسحها.
	if (para.ParagraphFormat.PageBreakBefore)
		para.ParagraphFormat.PageBreakBefore = false;

	//تحقق من كل عمليات التشغيل في الفقرة بحثًا عن فواصل الصفحات وقم بإزالتها.
	foreach (Run run in para.Runs)
	{
		if (run.Text.Contains(ControlChar.PageBreak))
			run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
	}
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);        

```

## خاتمة

في هذا البرنامج التعليمي ، تعلمنا كيفية إزالة فواصل الصفحات من مستند باستخدام مكتبة Aspose.Words for .NET. باتباع الدليل خطوة بخطوة ، يجب أن تكون قادرًا الآن على تنفيذ هذه الوظيفة في مشاريع C # الخاصة بك. يمكن أن تساعدك إزالة فواصل الصفحات في الحفاظ على تخطيط وتنسيق متسقين في مستنداتك.
