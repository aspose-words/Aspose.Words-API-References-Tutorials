---
title: إزالة تذييلات رؤوس المصدر
linktitle: إزالة تذييلات رؤوس المصدر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية إزالة الرؤوس والتذييلات أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/remove-source-headers-footers/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة إزالة تذييلات رؤوس المصدر في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها أثناء إزالة الرؤوس والتذييلات من المستند المصدر.

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

## الخطوة 3: إزالة الرؤوس والتذييلات من أقسام المستند المصدر

 لإزالة الرؤوس والتذييلات من كل قسم في المستند المصدر، يمكنك التكرار عبر الأقسام باستخدام`foreach` حلقة واستدعاء`ClearHeadersFooters` طريقة.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## الخطوة 4: تعطيل إعداد "LinkToPrevious" لـ HeadersFooters

حتى بعد مسح الرؤوس والتذييلات من المستند المصدر، هناك احتمال أن يكون إعداد "LinkToPrevious" لـ`HeadersFooters` لا يزال من الممكن تعيينها. لتجنب هذا السلوك، تحتاج إلى تعيينه بشكل صريح`false` للقسم الأول`HeadersFooters` ملكية.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## الخطوة 5: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج مع تمكين ميزة إزالة تذييلات رؤوس المصدر باستخدام`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### مثال على التعليمات البرمجية المصدر لإزالة تذييلات رؤوس المصدر باستخدام Aspose.Words لـ .NET 

إليك الكود المصدري الكامل لميزة "إزالة تذييلات رؤوس المصدر" في لغة C# باستخدام Aspose.Words for .NET:


```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بإزالة الرؤوس والتذييلات من كل قسم من الأقسام في المستند المصدر.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// حتى بعد مسح الرؤوس والتذييلات من المستند المصدر، يتم تحديد الإعداد "LinkToPrevious".
	// لا يزال من الممكن تعيين HeadersFooters. سيؤدي هذا إلى استمرار الرؤوس والتذييلات من الوجهة
	// وثيقة. يجب ضبط هذا على خطأ لتجنب هذا السلوك.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
هذا كل شيء! لقد نجحت في تنفيذ ميزة إزالة تذييلات رؤوس المصدر باستخدام Aspose.Words لـ .NET. سيحتوي المستند النهائي على المحتوى المدمج مع إزالة الرؤوس والتذييلات من المستند المصدر.