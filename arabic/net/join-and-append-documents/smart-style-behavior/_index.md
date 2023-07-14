---
title: سلوك الأسلوب الذكي
linktitle: سلوك الأسلوب الذكي
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية الحفاظ على سلوك النمط الذكي عند الانضمام إلى مستندات Word وإلحاقها باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/smart-style-behavior/
---

سيرشدك هذا البرنامج التعليمي خلال عملية استخدام ميزة Smart Style Behavior في Aspose.Words for .NET. تتيح لك هذه الميزة الانضمام إلى مستندات Word وإلحاقها مع الحفاظ على سلوك النمط الذكي.

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

 بعد ذلك ، تحتاج إلى تحميل مستندات المصدر والوجهة باستخدام Aspose.Words`Document` فصل. قم بتحديث أسماء الملفات في`Document` منشئ وفقًا لأسماء المستندات الخاصة بك.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: أدخل فاصل صفحة في مستند الوجهة

 للتأكد من ظهور المحتوى المُلحق على صفحة جديدة في المستند الوجهة ، يمكنك إدراج فاصل صفحة باستخدام ملف`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## الخطوة 4: تعيين خيارات سلوك النمط الذكي

 لتمكين سلوك النمط الذكي أثناء عملية الإلحاق ، تحتاج إلى إنشاء مثيل لـ`ImportFormatOptions` وضبط`SmartStyleBehavior` ملكية ل`true`.

```csharp
ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
```

## الخطوة 5: قم بإلحاق المستند المصدر بمستند الوجهة

 الآن ، يمكنك إلحاق المستند المصدر بالمستند الوجهة باستخدام ملف`InsertDocument` طريقة`DocumentBuilder` فصل. استخدم ال`ImportFormatMode.UseDestinationStyles` المعلمة وتمرير`ImportFormatOptions` كائن للحفاظ على أسلوب السلوك الذكي.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## الخطوة 6: احفظ المستند النهائي

 أخيرًا ، احفظ المستند المدمج مع تمكين ميزة Smart Style Behavior باستخدام ملف`Save` طريقة`Document` فصل.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

### مثال على شفرة المصدر لسلوك النمط الذكي باستخدام Aspose.Words for .NET

إليك شفرة المصدر الكاملة لميزة "سلوك النمط الذكي" في C # باستخدام Aspose.Words for .NET:
 
```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	ImportFormatOptions options = new ImportFormatOptions { SmartStyleBehavior = true };
	builder.InsertDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.SmartStyleBehavior.docx");
```

هذا كل شيء! لقد نجحت في تنفيذ ميزة Smart Style Behavior باستخدام Aspose.Words for .NET. سيحتوي المستند النهائي على المحتوى المدمج مع الحفاظ على سلوك النمط الذكي.