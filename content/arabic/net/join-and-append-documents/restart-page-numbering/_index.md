---
title: إعادة تشغيل ترقيم الصفحات
linktitle: إعادة تشغيل ترقيم الصفحات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إعادة تشغيل ترقيم الصفحات أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/restart-page-numbering/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة "إعادة تشغيل ترقيم الصفحات" في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها أثناء إعادة تشغيل ترقيم الصفحات في المستند المصدر.

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

 بعد ذلك، تحتاج إلى تحميل المستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في`Document` مُنشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: قم بتعيين المستند المصدر لإعادة تشغيل ترقيم الصفحات

 لإعادة تشغيل ترقيم الصفحات في المستند المصدر، تحتاج إلى تعيين`SectionStart` خاصية القسم الأول في الوثيقة المصدر ل`SectionStart.NewPage` وتعيين`RestartPageNumbering`الملكية ل`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## الخطوة 4: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج مع تمكين ميزة "إعادة تشغيل ترقيم الصفحات" باستخدام`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### مثال على التعليمات البرمجية المصدر لإعادة تشغيل ترقيم الصفحات باستخدام Aspose.Words لـ .NET

إليك الكود المصدري الكامل لميزة "إعادة تشغيل ترقيم الصفحات" في لغة C# باستخدام Aspose.Words for .NET:
 

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة "إعادة تشغيل ترقيم الصفحات" باستخدام Aspose.Words لـ .NET. سيحتوي المستند النهائي على المحتوى المدمج مع إعادة تشغيل ترقيم الصفحات في المستند المصدر.