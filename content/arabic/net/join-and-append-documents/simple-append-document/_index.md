---
title: وثيقة إلحاق بسيطة
linktitle: وثيقة إلحاق بسيطة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ضم مستندات Word وإلحاقها بالتنسيق المحفوظ باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/simple-append-document/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Simple Append Document في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها دون أي خيارات إضافية.

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

## الخطوة 3: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 4: احفظ المستند النهائي

 أخيرًا، احفظ المستند المدمج باستخدام ميزة Simple Append Document باستخدام الملف`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### مثال على التعليمات البرمجية المصدر لمستند الإلحاق البسيط باستخدام Aspose.Words لـ .NET

إليك الكود المصدري الكامل لميزة "إلحاق مستند بسيط" في لغة C# باستخدام Aspose.Words for .NET:

```csharp
	// المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// قم بإلحاق المستند المصدر بالمستند الوجهة بدون أي خيارات إضافية.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة إلحاق مستند بسيط باستخدام Aspose.Words لـ .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الحفاظ على تنسيق المصدر.