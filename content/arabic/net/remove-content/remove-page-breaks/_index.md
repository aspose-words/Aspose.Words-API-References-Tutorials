---
title: إزالة فواصل الصفحات في مستند Word
linktitle: إزالة فواصل الصفحات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إزالة فواصل الصفحات في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. اتبع دليلنا خطوة بخطوة للحصول على تخطيط سلس.
type: docs
weight: 10
url: /ar/net/remove-content/remove-page-breaks/
---
في هذا البرنامج التعليمي، سوف نستكشف كيفية إزالة فواصل الصفحات في مستند Word باستخدام مكتبة Aspose.Words for .NET. قد تتداخل فواصل الصفحات أحيانًا مع تنسيق المستند وتخطيطه، وقد يكون من الضروري إزالتها برمجيًا. سنقدم لك دليلًا خطوة بخطوة لمساعدتك على فهم العملية وتنفيذها في مشاريع C# الخاصة بك.

## متطلبات

قبل أن نبدأ، تأكد من أن لديك ما يلي:

- المعرفة الأساسية بلغة البرمجة C#
- تم تثبيت Aspose.Words لمكتبة .NET
- تم إعداد Visual Studio أو أي بيئة تطوير أخرى لـ C#

## الخطوة 1: إعداد البيئة

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET بشكل صحيح في مشروعك.

## الخطوة 2: تحميل المستند

لإزالة فواصل الصفحات من مستند، نحتاج أولاً إلى تحميل المستند في الذاكرة. يوضح التعليمة البرمجية التالية كيفية تحميل مستند من دليل محدد:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى المستند الخاص بك.

## الخطوة 3: إزالة فواصل الصفحات

بمجرد تحميل المستند، يمكننا البدء في إزالة فواصل الصفحات. يوضح مقتطف الشفرة أدناه كيفية تكرار جميع الفقرات في المستند، والتحقق من فواصل الصفحات، وإزالتها:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
     // إذا كانت الفقرة تحتوي على فاصل صفحات من قبل، فقم بمسحها
     if (para.ParagraphFormat.PageBreakBefore)
         para.ParagraphFormat.PageBreakBefore = false;

     // تحقق من كافة عمليات التشغيل في الفقرة بحثًا عن فواصل الصفحات وقم بإزالتها
     foreach(Run run in para.Runs)
     {
         if (run.Text.Contains(ControlChar.PageBreak))
             run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
     }
}
```

يتكرر مقتطف الكود أعلاه خلال جميع الفقرات الموجودة في المستند ويتحقق مما إذا كانت كل فقرة تحتوي على فاصل صفحات قبلها. إذا تم الكشف عن فاصل الصفحات، فسيتم مسحه. بعد ذلك، يقوم بالتحقق من كل تشغيل داخل الفقرة بحثًا عن فواصل الصفحات وإزالتها.

## الخطوة 4: حفظ المستند المعدل

بعد إزالة فواصل الصفحات، نحتاج إلى حفظ المستند المعدل. يوضح التعليمة البرمجية التالية كيفية حفظ المستند المعدل في موقع محدد:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 يستبدل`"modified-document.docx"`بالاسم المطلوب للمستند المعدل.

### نموذج التعليمات البرمجية المصدر لإزالة فواصل الصفحات باستخدام Aspose.Words لـ .NET 
```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");

NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
	// إذا كانت الفقرة تحتوي على فاصل صفحات قبل المجموعة، فقم بمسحها.
	if (para.ParagraphFormat.PageBreakBefore)
		para.ParagraphFormat.PageBreakBefore = false;

	// تحقق من كافة عمليات التشغيل في الفقرة بحثًا عن فواصل الصفحات وقم بإزالتها.
	foreach (Run run in para.Runs)
	{
		if (run.Text.Contains(ControlChar.PageBreak))
			run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
	}
}

doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);        

```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إزالة فواصل الصفحات من مستند باستخدام مكتبة Aspose.Words for .NET. باتباع الدليل الموضح خطوة بخطوة، من المفترض أن تكون الآن قادرًا على تنفيذ هذه الوظيفة في مشاريع C# الخاصة بك. يمكن أن تساعدك إزالة فواصل الصفحات في الحفاظ على تخطيط وتنسيق متسقين في مستنداتك.

### الأسئلة الشائعة

#### س: لماذا يجب علي استخدام Aspose.Words لإزالة فواصل الصفحات في مستند Word؟

ج: Aspose.Words هي مكتبة فئة قوية ومتعددة الاستخدامات لمعالجة مستندات Word في تطبيقات .NET. باستخدام Aspose.Words، يمكنك الحصول على حل فعال وسهل لإزالة فواصل الصفحات من مستنداتك. يتيح لك ذلك تخصيص تخطيط مستنداتك، وإزالة فواصل الصفحات غير المرغوب فيها، والحفاظ على عرض تقديمي متسق.

#### س: كيف يمكنني تحميل مستند في Aspose.Words لـ .NET؟

ج: لإزالة فواصل الصفحات في مستند Word، يجب عليك أولاً تحميل المستند إلى الذاكرة باستخدام أسلوب Load() الخاص بـ Aspose.Words. إليك نموذج التعليمات البرمجية لتحميل مستند من دليل محدد:

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// قم بتحميل المستند
Document doc = new Document(dataDir + "your-document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي إلى المستند الخاص بك.

#### س: كيفية إزالة فواصل الصفحات في مستند باستخدام Aspose.Words؟

ج: بمجرد تحميل المستند، يمكنك البدء في إزالة فواصل الصفحات. استخدم حلقة لتكرار جميع الفقرات في المستند، وتحقق مما إذا كانت تحتوي على فواصل صفحات وقم بإزالتها إذا لزم الأمر. هنا نموذج التعليمات البرمجية:

```csharp
NodeCollection paragraphs = doc.GetChildNodes(NodeType.Paragraph, true);

foreach (Paragraph para in paragraphs)
{
      // إذا كانت الفقرة تحتوي على فاصل صفحات من قبل، فقم بإزالته
      if (para.ParagraphFormat.PageBreakBefore)
          para.ParagraphFormat.PageBreakBefore = false;

      // تحقق من كافة عناصر التشغيل في الفقرة بحثًا عن فواصل الصفحات وقم بإزالتها
      foreach(Run run in para.Runs)
      {
          if (run.Text.Contains(ControlChar.PageBreak))
              run.Text = run.Text.Replace(ControlChar.PageBreak, string.Empty);
      }
}
```

يتكرر هذا الرمز خلال كافة الفقرات الموجودة في المستند، ويتحقق مما إذا كانت تحتوي على فاصل صفحات بادئ، ثم يقوم بإزالته. ثم يقوم بالتحقق من كل عنصر تشغيل في الفقرة بحثًا عن فواصل الصفحات وإزالتها.

#### س: كيف يتم حفظ المستند الذي تم تحريره في Aspose.Words لـ .NET؟

ج: بعد إزالة فواصل الصفحات، تحتاج إلى حفظ المستند المعدل. استخدم طريقة Save() لحفظ المستند المعدل في موقع محدد. هنا نموذج التعليمات البرمجية:

```csharp
doc.Save(dataDir + "modified-document.docx", SaveFormat.Docx);
```

 يستبدل`"modified-document.docx"`بالاسم المطلوب للمستند المعدل.