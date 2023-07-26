---
title: إزالة تذييلات رؤوس المصدر
linktitle: إزالة تذييلات رؤوس المصدر
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إزالة الرؤوس والتذييلات أثناء الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/remove-source-headers-footers/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Remove Source Headers Footers في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها أثناء إزالة الرؤوس والتذييلات من المستند المصدر.

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

 بعد ذلك ، تحتاج إلى تحميل مستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في ملف`Document` المُنشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: إزالة الرؤوس والتذييلات من أقسام المستند المصدر

 لإزالة الرؤوس والتذييلات من كل قسم في المستند المصدر ، يمكنك التكرار خلال الأقسام باستخدام ملف`foreach` حلقة واستدعاء`ClearHeadersFooters` طريقة.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## الخطوة 4: تعطيل إعداد "LinkToPrevious" لـ HeadersFooters

 حتى بعد مسح الرؤوس والتذييلات من المستند المصدر ، هناك احتمال أن يكون إعداد "LinkToPrevious"`HeadersFooters` لا يزال من الممكن تعيينها. لتجنب هذا السلوك ، تحتاج إلى تعيينه صراحةً على`false` للقسم الأول`HeadersFooters` ملكية.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## الخطوة 5: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 6: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع تمكين ميزة Remove Source Headers Footers باستخدام ملحق`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### مثال على شفرة المصدر لإزالة تذييلات رؤوس المصدر باستخدام Aspose.Words for .NET 

إليك شفرة المصدر الكاملة لميزة "إزالة تذييلات رؤوس المصدر" في C # باستخدام Aspose.Words for .NET:


```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بإزالة الرؤوس والتذييلات من كل قسم في المستند المصدر.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// حتى بعد مسح الرؤوس والتذييلات من المستند المصدر ، فإن الإعداد "LinkToPrevious"
	// لا يزال من الممكن تعيين HeadersFooters. سيؤدي هذا إلى استمرار الرؤوس والتذييلات من الوجهة
	// وثيقة. يجب تعيين هذا على خطأ لتجنب هذا السلوك.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
هذا كل شيء! لقد نجحت في تنفيذ ميزة Remove Source Headers Footers باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع إزالة الرؤوس والتذييلات من المستند المصدر.