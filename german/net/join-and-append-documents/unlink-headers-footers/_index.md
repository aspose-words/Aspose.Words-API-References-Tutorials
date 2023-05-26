---
title: فك ارتباط تذييلات الرؤوس
linktitle: فك ارتباط تذييلات الرؤوس
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية الانضمام إلى مستندات Word وإلحاقها أثناء إلغاء ربط الرؤوس والتذييلات باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/join-and-append-documents/unlink-headers-footers/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Unlink Headers Footers في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها أثناء إلغاء ربط الرؤوس والتذييلات من المستند المصدر.

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

## الخطوة 3: إلغاء ربط الرؤوس والتذييلات في المستند المصدر

 لإلغاء ارتباط الرؤوس والتذييلات في المستند المصدر من متابعة رؤوس وتذييلات المستند الوجهة ، تحتاج إلى تعيين`LinkToPrevious` ممتلكات`HeadersFooters` المجموعة في القسم الأول من المستند المصدر إلى`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## الخطوة 4: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع تمكين ميزة Unlink Headers Footers باستخدام ملحق`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### مثال على شفرة المصدر لإلغاء ربط تذييلات الرؤوس باستخدام Aspose.Words for .NET

إليك شفرة المصدر الكاملة لميزة "Unlink Headers Footers" في C # باستخدام Aspose.Words for .NET:

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بفك ارتباط الرؤوس والتذييلات في المستند المصدر لإيقاف ذلك
	// من متابعة رؤوس وتذييلات المستند الوجهة.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة Unlink Headers Footers باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الرؤوس والتذييلات من المستند المصدر غير المرتبط بالمستند الوجهة.