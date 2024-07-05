---
title: إلغاء ربط الرؤوس والتذييلات
linktitle: إلغاء ربط الرؤوس والتذييلات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية الانضمام إلى مستندات Word وإلحاقها أثناء إلغاء ربط الرؤوس والتذييلات باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/unlink-headers-footers/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Unlink Headers Footers في Aspose.Words for .NET. تسمح لك هذه الميزة بالانضمام إلى مستندات Word وإلحاقها أثناء إلغاء ربط الرؤوس والتذييلات من المستند المصدر.

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

## الخطوة 3: قم بإلغاء ربط الرؤوس والتذييلات في المستند المصدر

 لإلغاء ربط الرؤوس والتذييلات في المستند المصدر من متابعة رؤوس وتذييلات المستند الوجهة، تحتاج إلى تعيين`LinkToPrevious` ملكية`HeadersFooters` جمع في القسم الأول من الوثيقة المصدر ل`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## الخطوة 4: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج مع تمكين ميزة Unlink Headers Footers باستخدام`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### مثال على التعليمات البرمجية المصدر لإلغاء ربط تذييلات الرؤوس باستخدام Aspose.Words لـ .NET

إليك الكود المصدري الكامل لميزة "Unlink Headers Footers" في لغة C# باستخدام Aspose.Words for .NET:

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بإلغاء ربط الرؤوس والتذييلات في المستند المصدر لإيقاف ذلك
	// من متابعة رؤوس وتذييلات المستند الوجهة.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة إلغاء ربط الرؤوس والتذييلات باستخدام Aspose.Words لـ .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الرؤوس والتذييلات من المستند المصدر غير المرتبط بالمستند الوجهة.