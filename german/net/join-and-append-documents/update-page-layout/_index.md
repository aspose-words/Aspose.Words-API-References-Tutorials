---
title: تحديث تخطيط الصفحة
linktitle: تحديث تخطيط الصفحة
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تحديث تخطيط الصفحة عند الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/join-and-append-documents/update-page-layout/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة تحديث تخطيط الصفحة في Aspose.Words for .NET. تضمن هذه الميزة تحديث تخطيط الصفحة بشكل صحيح عند الانضمام إلى مستندات Word وإلحاقها.

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

## الخطوة 3: تحديث تخطيط الصفحة لمستند الوجهة

 للتأكد من تحديث تخطيط الصفحة بشكل صحيح قبل إلحاق المستند المصدر ، يمكنك استدعاء`UpdatePageLayout` الطريقة في المستند الوجهة.

```csharp
dstDoc.UpdatePageLayout();
```

## الخطوة 4: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: تحديث تخطيط الصفحة مرة أخرى

 بعد إلحاق المستند المصدر ، تحتاج إلى استدعاء`UpdatePageLayout`على المستند الوجهة مرة أخرى للتأكد من أن أي تغييرات يتم إجراؤها بعد عملية الإلحاق تنعكس في الإخراج المقدم.

```csharp
dstDoc.UpdatePageLayout();
```

## الخطوة 6: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع تمكين ميزة تحديث تخطيط الصفحة باستخدام ملحق`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### مثال على شفرة المصدر لتحديث تخطيط الصفحة باستخدام Aspose.Words for .NET

إليك شفرة المصدر الكاملة لميزة "تحديث تخطيط الصفحة" في C # باستخدام Aspose.Words for .NET:

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// إذا تم تحويل المستند الوجهة إلى PDF ، أو صورة ، إلخ.
	// أو يتم استدعاء UpdatePageLayout قبل المستند المصدر. مُلحق ،
	// ثم أي تغييرات يتم إجراؤها بعد ذلك لن تنعكس في الإخراج المقدم
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// لكي يتم تحديث التغييرات لتقديم الإخراج ، يجب استدعاء UpdatePageLayout مرة أخرى.
	// إذا لم يتم الاتصال به مرة أخرى ، فلن يظهر المستند المُلحق في إخراج العرض التالي.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة تحديث تخطيط الصفحة باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع تحديث تخطيط الصفحة بشكل صحيح.