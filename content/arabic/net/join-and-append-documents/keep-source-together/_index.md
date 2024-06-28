---
title: احتفظ بالمصدر معًا
linktitle: احتفظ بالمصدر معًا
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استخدام Aspose.Words for .NET لضم مستندات Word وإلحاقها مع الاحتفاظ بالمحتوى المصدر مع المستند الوجهة.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/keep-source-together/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Keep Source Together في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word متعددة وإلحاقها مع الاحتفاظ بمحتوى المستند المصدر مع محتوى المستند الوجهة. 

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت Aspose.Words لـ .NET. يمكنك تنزيله من موقع Aspose أو تثبيته عبر NuGet.
2. Visual Studio أو أي بيئة تطوير أخرى لـ C#.

## الخطوة 1: تهيئة أدلة المستندات

 أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. تعديل قيمة`dataDir` متغير إلى المسار حيث توجد المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستندات المصدر والوجهة

بعد ذلك، تحتاج إلى تحميل المستندات المصدر والوجهة باستخدام Aspose.Words.`Document` فصل. قم بتحديث أسماء الملفات في`Document` مُنشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## الخطوة 3: قم بتعيين المستند المصدر ليظهر بعد محتوى مستند الوجهة

 للتأكد من ظهور المستند المصدر مباشرةً بعد محتوى المستند الوجهة، يلزمك تعيين الإعداد`SectionStart` خاصية القسم الأول في الوثيقة المصدر ل`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: قم بتعيين تنسيق الفقرة "الاحتفاظ بالتالي" للمستند المصدر

 للاحتفاظ بالفقرات في المستند المصدر معًا، يمكنك التكرار خلال كل فقرة في المستند وتعيين`KeepWithNext`الملكية ل`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## الخطوة 5: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج مع تمكين ميزة "الاحتفاظ بالمصدر معًا" باستخدام`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### مثال على التعليمات البرمجية المصدر لـ Keep Source Together باستخدام Aspose.Words لـ .NET 

إليك الكود المصدري الكامل لميزة "الاحتفاظ بالمصدر معًا" في لغة C# باستخدام Aspose.Words for .NET:


```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// قم بتعيين المستند المصدر ليظهر مباشرة بعد محتوى المستند الوجهة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة Keep Source Together باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الاحتفاظ بالفقرات الموجودة في المستند المصدر معًا.