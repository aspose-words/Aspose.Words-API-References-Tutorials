---
title: إعداد صفحة مختلفة
linktitle: إعداد صفحة مختلفة
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إلحاق مستند بإعدادات إعداد صفحة مختلفة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/different-page-setup/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق مستند بإعدادات صفحة مختلفة بمستند آخر. يوضح كود المصدر المقدم كيفية إعداد إعدادات صفحة مختلفة لمستندات المصدر والوجهة والتأكد من المتابعة والترقيم المناسبين.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من موقع Aspose الرسمي أو استخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح مستندات المصدر والوجهة

 افتح مستندات المصدر والوجهة باستخدام ملف`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: قم بإعداد إعدادات الصفحة للمستند المصدر

اضبط إعدادات إعداد الصفحة للمستند المصدر لضمان المتابعة والترقيم المناسبين. في هذا المثال ، قمنا بتعيين بداية القسم إلى`SectionStart.Continuous` وأعد ترقيم الصفحات. نتأكد أيضًا من تطابق عرض الصفحة وارتفاعها واتجاهها مع القسم الأخير من المستند الوجهة.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## الخطوة 4: تعديل تنسيق الفقرة

 للحفاظ على التنسيق الصحيح ، كرر عبر جميع الفقرات في المستند المصدر وقم بتعيين ملف`KeepWithNext` ملكية ل`true`. هذا يضمن بقاء الفقرات معًا أثناء عملية الإلحاق.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## الخطوة 5: قم بإلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument` طريقة المستند الوجهة لإلحاق المستند المصدر المعدل بالمستند الوجهة ، مع الحفاظ على تنسيق المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ المستند الوجهة

 أخيرًا ، احفظ مستند الوجهة المعدل باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

هذا يكمل تنفيذ إلحاق مستند بإعدادات إعداد صفحة مختلفة باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لإعداد صفحة مختلفة باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//قم بتعيين المستند المصدر للمتابعة مباشرة بعد نهاية المستند الوجهة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// أعد تشغيل ترقيم الصفحات في بداية المستند المصدر.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// لضمان عدم حدوث ذلك عندما يحتوي المستند المصدر على إعدادات إعداد صفحة مختلفة ، تأكد من أن
	// الإعدادات متطابقة بين القسم الأخير من المستند الوجهة.
	// إذا كانت هناك أقسام أخرى مستمرة تتبع في المستند المصدر ،
	// هذا سوف يحتاج إلى أن يتكرر لتلك الأقسام.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// كرر خلال جميع الأقسام في المستند المصدر.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```