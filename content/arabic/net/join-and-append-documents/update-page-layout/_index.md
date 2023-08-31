---
title: تحديث تخطيط الصفحة
linktitle: تحديث تخطيط الصفحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تحديث تخطيط الصفحة عند الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/update-page-layout/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة تحديث تخطيط الصفحة في Aspose.Words for .NET. تضمن هذه الميزة تحديث تخطيط الصفحة بشكل صحيح عند الانضمام إلى مستندات Word وإلحاقها.

## المتطلبات الأساسية

قبل أن تبدأ، تأكد من أن لديك ما يلي:

1. تم تثبيت Aspose.Words لـ .NET. يمكنك تنزيله من موقع Aspose أو تثبيته عبر NuGet.
2. Visual Studio أو أي بيئة تطوير أخرى لـ C#.

## الخطوة 1: تهيئة أدلة المستندات

 أولاً، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. تعديل قيمة`dataDir`متغير إلى المسار حيث توجد المستندات الخاصة بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل مستندات المصدر والوجهة

 بعد ذلك، تحتاج إلى تحميل المستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في`Document` مُنشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: تحديث تخطيط الصفحة للمستند الوجهة

 للتأكد من تحديث تخطيط الصفحة بشكل صحيح قبل إلحاق المستند المصدر، يمكنك استدعاء`UpdatePageLayout` الطريقة في المستند الوجهة.

```csharp
dstDoc.UpdatePageLayout();
```

## الخطوة 4: إلحاق المستند المصدر بالمستند الوجهة

 الآن، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام الملف`AppendDocument` طريقة`Document` فصل. ال`ImportFormatMode.KeepSourceFormatting` تضمن المعلمة الحفاظ على تنسيق المصدر أثناء عملية الإلحاق.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## الخطوة 5: تحديث تخطيط الصفحة مرة أخرى

 بعد إلحاق المستند المصدر، يجب عليك الاتصال بـ`UpdatePageLayout` الطريقة على المستند الوجهة مرة أخرى للتأكد من أن أي تغييرات يتم إجراؤها بعد عملية الإلحاق تنعكس في المخرجات المقدمة.

```csharp
dstDoc.UpdatePageLayout();
```

## الخطوة 6: احفظ الوثيقة النهائية

 أخيرًا، احفظ المستند المدمج مع تمكين ميزة تحديث تخطيط الصفحة باستخدام`Save` طريقة`Document` فصل.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

### مثال على التعليمات البرمجية المصدر لتحديث تخطيط الصفحة باستخدام Aspose.Words لـ .NET

إليك الكود المصدري الكامل لميزة "تحديث تخطيط الصفحة" في لغة C# باستخدام Aspose.Words for .NET:

```csharp
	//المسار إلى دليل المستندات الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	//إذا تم تقديم المستند الوجهة إلى PDF أو صورة وما إلى ذلك.
	// أو يتم استدعاء UpdatePageLayout قبل المستند المصدر. تم إلحاقه،
	// فإن أي تغييرات يتم إجراؤها بعد ذلك لن تنعكس في الإخراج المقدم
	dstDoc.UpdatePageLayout();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	// لكي يتم تحديث التغييرات إلى المخرجات المقدمة، يجب استدعاء UpdatePageLayout مرة أخرى.
	// إذا لم يتم استدعاؤه مرة أخرى، فلن يظهر المستند الملحق في مخرجات العرض التالي.
	dstDoc.UpdatePageLayout();
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UpdatePageLayout.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة تحديث تخطيط الصفحة باستخدام Aspose.Words لـ .NET. سيحتوي المستند النهائي على المحتوى المدمج مع تحديث تخطيط الصفحة بشكل صحيح.