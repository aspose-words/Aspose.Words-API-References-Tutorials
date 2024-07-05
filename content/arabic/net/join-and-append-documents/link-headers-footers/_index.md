---
title: ربط الرؤوس والتذييلات
linktitle: ربط الرؤوس والتذييلات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ربط الرؤوس والتذييلات أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/link-headers-footers/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Link Headers Footers في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word متعددة وإلحاقها أثناء ربط رؤوس وتذييلات المستند المصدر بالقسم السابق في المستند الوجهة.

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

## الخطوة 3: قم بتعيين المستند الملحق ليظهر على صفحة جديدة

 للتأكد من ظهور المحتوى من المستند المصدر على صفحة جديدة في المستند الوجهة، تحتاج إلى تعيين الإعداد`SectionStart` خاصية القسم الأول في الوثيقة المصدر ل`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## الخطوة 4: ربط الرؤوس والتذييلات بالقسم السابق

 لربط رؤوس وتذييلات المستند المصدر بالقسم السابق في المستند الوجهة، يمكنك استخدام الأمر`LinkToPrevious` طريقة`HeadersFooters` مجموعة. بالمرور`true` كمعلمة، يمكنك تجاوز أي رؤوس أو تذييلات موجودة في المستند المصدر.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## الخطوة 5: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج بالرؤوس والتذييلات المرتبطة باستخدام الملف`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### مثال على التعليمات البرمجية المصدر لتذييلات رؤوس الارتباطات باستخدام Aspose.Words لـ .NET 

إليك الكود المصدري الكامل لميزة "Link Headers Footers" في لغة C# باستخدام Aspose.Words for .NET:


```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بتعيين المستند الملحق ليظهر في صفحة جديدة.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// قم بربط الرؤوس والتذييلات في المستند المصدر بالقسم السابق.
	// سيؤدي هذا إلى تجاوز أي رؤوس أو تذييلات موجودة بالفعل في المستند المصدر.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة Link Headers Footers باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الرؤوس والتذييلات من المستند المصدر المرتبط بالقسم السابق في المستند الوجهة.