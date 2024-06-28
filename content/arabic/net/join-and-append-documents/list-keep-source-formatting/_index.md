---
title: قائمة الاحتفاظ بتنسيق المصدر
linktitle: قائمة الاحتفاظ بتنسيق المصدر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية الحفاظ على تنسيق القائمة أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/list-keep-source-formatting/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة List Keep Source Formatting في Aspose.Words for .NET. تسمح لك هذه الميزة بالانضمام إلى مستندات Word وإلحاقها مع الحفاظ على التنسيق المصدر للقوائم.

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

## الخطوة 3: قم بتعيين المستند المصدر للتدفق المستمر

 للتأكد من أن المحتوى من المستند المصدر يتدفق بشكل مستمر عند إلحاقه بالمستند الوجهة، تحتاج إلى تعيين`SectionStart` خاصية القسم الأول في الوثيقة المصدر ل`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting`تضمن المعلمة الحفاظ على تنسيق المصدر، بما في ذلك تنسيق القوائم، أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج مع تمكين ميزة تنسيق الاحتفاظ بالقائمة باستخدام الملف`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### مثال على التعليمات البرمجية المصدر لتنسيق قائمة الاحتفاظ بالمصدر باستخدام Aspose.Words لـ .NET 

إليك الكود المصدري الكامل لميزة List Keep Source Formatting في C# باستخدام Aspose.Words for .NET:

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// قم بإلحاق محتوى المستند بحيث يتدفق بشكل مستمر.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة تنسيق قائمة الاحتفاظ بالمصدر باستخدام Aspose.Words لـ .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الاحتفاظ بتنسيق قائمة المستند المصدر.