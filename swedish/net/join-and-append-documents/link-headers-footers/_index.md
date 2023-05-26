---
title: ربط تذييلات الرؤوس
linktitle: ربط تذييلات الرؤوس
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية ربط الرؤوس والتذييلات أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /sv/net/join-and-append-documents/link-headers-footers/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Link Headers Footers في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام وإلحاق مستندات Word متعددة أثناء ربط رؤوس وتذييلات المستند المصدر بالقسم السابق في المستند الوجهة.

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

## الخطوة 3: اضبط المستند المُلحق على الظهور في صفحة جديدة

للتأكد من ظهور المحتوى من المستند المصدر على صفحة جديدة في المستند الوجهة ، تحتاج إلى تعيين`SectionStart` من القسم الأول في المستند المصدر إلى`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## الخطوة 4: ربط الرؤوس والتذييلات بالقسم السابق

 لربط رؤوس وتذييلات المستند المصدر بالمقطع السابق في المستند الوجهة ، يمكنك استخدام ملف`LinkToPrevious` طريقة`HeadersFooters` مجموعة. بالمرور`true` كمعلمة ، يمكنك تجاوز أي رؤوس أو تذييلات موجودة في المستند المصدر.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## الخطوة 5: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع الرؤوس والتذييلات المرتبطة باستخدام ملف`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### مثال على شفرة المصدر لتذييلات رؤوس الروابط باستخدام Aspose.Words for .NET 

إليك شفرة المصدر الكاملة لميزة "Link Headers Footers" في C # باستخدام Aspose.Words for .NET:


```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بتعيين المستند المُلحق ليظهر في صفحة جديدة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// اربط الرؤوس والتذييلات في المستند المصدر بالمقطع السابق.
	// سيؤدي هذا إلى تجاوز أي رؤوس أو تذييلات موجودة بالفعل في المستند المصدر.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة Link Headers Footers باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الرؤوس والتذييلات من المستند المصدر المرتبط بالقسم السابق في المستند الوجهة.