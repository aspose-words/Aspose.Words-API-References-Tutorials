---
title: قائمة الاحتفاظ بتنسيق المصدر
linktitle: قائمة الاحتفاظ بتنسيق المصدر
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الحفاظ على تنسيق القائمة أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/list-keep-source-formatting/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة قائمة الاحتفاظ بتنسيق المصدر في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها مع الاحتفاظ بتنسيق المصدر للقوائم.

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## الخطوة 3: اضبط المستند المصدر على التدفق المستمر

 للتأكد من أن المحتوى من المستند المصدر يتدفق باستمرار عند إلحاقه بالمستند الوجهة ، تحتاج إلى تعيين`SectionStart` من القسم الأول في المستند المصدر إلى`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## الخطوة 4: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting`تضمن المعلمة الحفاظ على تنسيق المصدر ، بما في ذلك تنسيق القوائم ، أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع تمكين ميزة قائمة الاحتفاظ بتنسيق المصدر باستخدام ملحق`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

### مثال على شفرة المصدر لـ List Keep Source Formatting باستخدام Aspose.Words for .NET 

إليك شفرة المصدر الكاملة لميزة "الاحتفاظ بتنسيق المصدر" في قائمة C # باستخدام Aspose.Words for .NET:

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// قم بإلحاق محتوى المستند بحيث يتدفق باستمرار.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListKeepSourceFormatting.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة قائمة الاحتفاظ بتنسيق المصدر باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الاحتفاظ بتنسيق قائمة المستند المصدر.