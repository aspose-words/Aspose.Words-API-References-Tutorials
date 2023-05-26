---
title: أعد تشغيل ترقيم الصفحات
linktitle: أعد تشغيل ترقيم الصفحات
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية إعادة تشغيل ترقيم الصفحات أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/join-and-append-documents/restart-page-numbering/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة إعادة تشغيل ترقيم الصفحات في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها أثناء إعادة تشغيل ترقيم الصفحات في المستند المصدر.

## المتطلبات الأساسية

قبل أن تبدأ ، تأكد من أن لديك ما يلي:

1. تم تثبيت Aspose.Words for .NET. يمكنك تنزيله من موقع Aspose أو تثبيته عبر NuGet.
2. Visual Studio أو أي بيئة تطوير C # أخرى.

## الخطوة 1: تهيئة دلائل المستندات

 أولاً ، تحتاج إلى تعيين المسار إلى دليل المستند الخاص بك. قم بتعديل قيمة ملف`dataDir` متغير إلى المسار حيث توجد المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستندات المصدر والوجهة

 بعد ذلك ، تحتاج إلى تحميل مستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في ملف`Document` المُنشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: اضبط المستند المصدر على إعادة تشغيل ترقيم الصفحات

 لإعادة تشغيل ترقيم الصفحات في المستند المصدر ، تحتاج إلى ضبط`SectionStart` من القسم الأول في المستند المصدر إلى`SectionStart.NewPage` وضبط`RestartPageNumbering` ملكية ل`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## الخطوة 4: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع تمكين ميزة إعادة تشغيل ترقيم الصفحات باستخدام ملحق`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### مثال على شفرة المصدر لإعادة تشغيل ترقيم الصفحات باستخدام Aspose.Words for .NET

إليك شفرة المصدر الكاملة لميزة "إعادة تشغيل ترقيم الصفحات" في C # باستخدام Aspose.Words for .NET:
 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة إعادة تشغيل ترقيم الصفحات باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع إعادة تشغيل ترقيم الصفحات في المستند المصدر.