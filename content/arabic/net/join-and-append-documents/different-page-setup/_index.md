---
title: إعداد صفحة مختلفة
linktitle: إعداد صفحة مختلفة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إلحاق مستند بإعدادات مختلفة لإعداد الصفحة باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/different-page-setup/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإلحاق مستند بإعدادات مختلفة لإعداد الصفحة بمستند آخر. يوضح كود المصدر المقدم كيفية إعداد إعدادات الصفحة المختلفة للمستندات المصدر والوجهة وضمان المتابعة والترقيم بشكل صحيح.

## الخطوة 1: إعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تم تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله من[Aspose.Releases]https://releases.aspose.com/words/net/ أو استخدم مدير الحزم NuGet لتثبيته.
- مسار دليل المستند حيث توجد المستندات المصدر والوجهة.

## الخطوة 2: افتح المستندات المصدر والوجهة

 افتح المستندات المصدر والوجهة باستخدام`Document` منشئ الطبقة. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: قم بإعداد إعدادات الصفحة للمستند المصدر

اضبط إعدادات إعداد الصفحة للمستند المصدر لضمان المتابعة والترقيم بشكل صحيح. في هذا المثال، قمنا بتعيين بداية القسم على`SectionStart.Continuous` وأعد تشغيل ترقيم الصفحات. نتأكد أيضًا من أن عرض الصفحة وارتفاعها واتجاهها يتطابق مع القسم الأخير من المستند الوجهة.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## الخطوة 4: تعديل تنسيق الفقرة

 للحفاظ على التنسيق الصحيح، قم بالتكرار عبر كافة الفقرات في المستند المصدر وقم بتعيين`KeepWithNext` الملكية ل`true`. وهذا يضمن بقاء الفقرات معًا أثناء عملية الإلحاق.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## الخطوة 5: إلحاق المستند المصدر بالمستند الوجهة

 استخدم ال`AppendDocument` طريقة المستند الوجهة لإلحاق المستند المصدر المعدل بالمستند الوجهة، مع الحفاظ على تنسيق المصدر.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ مستند الوجهة

 وأخيرًا، احفظ مستند الوجهة المعدل باستخدام الملف`Save` طريقة`Document` هدف.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

يكمل هذا تنفيذ إلحاق مستند بإعدادات مختلفة لإعداد الصفحة باستخدام Aspose.Words لـ .NET.

### مثال على التعليمات البرمجية المصدر لإعداد صفحة مختلفة باستخدام Aspose.Words لـ .NET 

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//قم بتعيين المستند المصدر للمتابعة مباشرة بعد نهاية المستند الوجهة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// أعد تشغيل ترقيم الصفحات في بداية المستند المصدر.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// للتأكد من عدم حدوث ذلك عندما يحتوي المستند المصدر على إعدادات إعداد صفحة مختلفة، تأكد من أن
	// الإعدادات متطابقة بين القسم الأخير من المستند الوجهة.
	// إذا كان هناك المزيد من الأقسام المستمرة التي تتبع في المستند المصدر،
	// سيتعين تكرار هذا لتلك الأقسام.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// قم بالتكرار عبر جميع الأقسام في المستند المصدر.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```