---
title: الاحتفاظ بالمصدر معًا
linktitle: الاحتفاظ بالمصدر معًا
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية استخدام Aspose.Words for .NET للانضمام إلى مستندات Word وإلحاقها مع الاحتفاظ بالمحتوى المصدر مع المستند الوجهة.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/keep-source-together/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Keep Source Together في Aspose.Words for .NET. تسمح لك هذه الميزة بالانضمام إلى العديد من مستندات Word وإلحاقها مع الاحتفاظ بمحتوى المستند المصدر مع محتوى المستند الوجهة. 

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تم تثبيت Aspose.Words for .NET. يمكنك تنزيله من موقع Aspose أو تثبيته عبر NuGet.
2. Visual Studio أو أي بيئة تطوير C # أخرى.

## الخطوة 1: تهيئة دلائل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى دليل المستند الخاص بك. قم بتعديل قيمة ملف`dataDir`متغير إلى المسار حيث توجد المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستندات المصدر والوجهة

 بعد ذلك ، تحتاج إلى تحميل مستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في`Document` منشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## الخطوة 3: اضبط المستند المصدر على الظهور بعد محتوى وثيقة الوجهة

 للتأكد من ظهور المستند المصدر مباشرةً بعد محتوى المستند الوجهة ، تحتاج إلى تعيين ملف`SectionStart` من القسم الأول في المستند المصدر إلى`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: قم بتعيين تنسيق الفقرة "Keep with Next" لمستند المصدر

 للاحتفاظ بالفقرات في المستند المصدر معًا ، يمكنك تكرار كل فقرة في المستند وتعيين ملف`KeepWithNext` الملكية ل`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## الخطوة 5: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ المستند النهائي

أخيرًا ، احفظ المستند المدمج مع تمكين ميزة "الاحتفاظ بالمصدر معًا" باستخدام`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### مثال على شفرة المصدر لـ Keep Source Together باستخدام Aspose.Words for .NET 

إليك شفرة المصدر الكاملة لميزة "Keep Source Together" في C # باستخدام Aspose.Words for .NET:


```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// اضبط الوثيقة المصدر لتظهر مباشرة بعد محتوى الوثيقة الوجهة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة Keep Source Together باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الاحتفاظ بالفقرات الموجودة في المستند المصدر معًا.