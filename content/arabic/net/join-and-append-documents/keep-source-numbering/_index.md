---
title: احتفظ بترقيم المصدر
linktitle: احتفظ بترقيم المصدر
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية استيراد المستندات مع الحفاظ على التنسيق باستخدام Aspose.Words لـ .NET. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية.
type: docs
weight: 10
url: /ar/net/join-and-append-documents/keep-source-numbering/
---
## مقدمة

 عند العمل مع Aspose.Words for .NET، يمكن التعامل مع استيراد المستندات من مصدر إلى آخر مع الحفاظ على التنسيق بكفاءة باستخدام`NodeImporter` فصل. سيرشدك هذا البرنامج التعليمي خلال العملية خطوة بخطوة.

## المتطلبات الأساسية

قبل البدء، تأكد من أن لديك ما يلي:
- تم تثبيت Visual Studio على جهازك.
-  تم تثبيت Aspose.Words لـ .NET. إذا لم يكن الأمر كذلك، قم بتنزيله من[هنا](https://releases.aspose.com/words/net/).
- المعرفة الأساسية ببرمجة C# و.NET.

## استيراد مساحات الأسماء

أولاً، قم بتضمين مساحات الأسماء الضرورية في مشروعك:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## الخطوة 1: قم بإعداد مشروعك

ابدأ بإنشاء مشروع C# جديد في Visual Studio وقم بتثبيت Aspose.Words عبر NuGet Package Manager.

## الخطوة 2: تهيئة المستندات
إنشاء مثيلات للمصدر (`srcDoc`) والوجهة (`dstDoc`) وثائق.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## الخطوة 3: تكوين خيارات الاستيراد
قم بإعداد خيارات الاستيراد للحفاظ على تنسيق المصدر، بما في ذلك الفقرات المرقمة.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## الخطوة 4: استيراد الفقرات
قم بالتكرار خلال الفقرات الموجودة في المستند المصدر وقم باستيرادها إلى المستند الوجهة.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## الخطوة 5: احفظ المستند
احفظ المستند المدمج في الموقع الذي تريده.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## خاتمة

 في الختام، يعد استخدام Aspose.Words لـ .NET لاستيراد المستندات مع الحفاظ على التنسيق أمرًا مباشرًا مع`NodeImporter` فصل. تضمن هذه الطريقة أن تحافظ مستنداتك على مظهرها الأصلي وبنيتها بسلاسة.

## الأسئلة الشائعة

### هل يمكنني استيراد المستندات بأنماط تنسيق مختلفة؟
 نعم`NodeImporter` يدعم الفصل استيراد المستندات ذات أنماط التنسيق المتنوعة.

### ماذا لو كانت مستنداتي تحتوي على جداول وصور معقدة؟
يتعامل Aspose.Words for .NET مع الهياكل المعقدة مثل الجداول والصور أثناء عمليات الاستيراد.

### هل Aspose.Words متوافق مع كافة إصدارات .NET؟
يدعم Aspose.Words إصدارات .NET Framework و.NET Core لتحقيق التكامل السلس.

### كيف يمكنني معالجة الأخطاء أثناء استيراد المستندات؟
استخدم كتل محاولة الالتقاط لمعالجة الاستثناءات التي قد تحدث أثناء عملية الاستيراد.

### أين يمكنني العثور على مزيد من الوثائق التفصيلية حول Aspose.Words لـ .NET؟
 قم بزيارة[توثيق](https://reference.aspose.com/words/net/) للحصول على أدلة شاملة ومراجع API.
