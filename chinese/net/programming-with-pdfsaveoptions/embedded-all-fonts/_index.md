---
title: جميع الخطوط المضمنة
linktitle: جميع الخطوط المضمنة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتضمين كل الخطوط في ملف PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/embedded-all-fonts/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة Embedded All Fonts في Aspose.Words for .NET. سنستعرض مقتطف الشفرة ونوضح كل جزء بالتفصيل. بنهاية هذا البرنامج التعليمي ، ستكون قادرًا على فهم كيفية تضمين جميع الخطوط في مستند وإنشاء ملف PDF مع الخطوط المضمنة باستخدام Aspose.Words for .NET.

قبل أن نبدأ ، تأكد من تثبيت وإعداد مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد مسار دليل المستند

للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد المستندات الخاصة بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستند الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يحمل اسم "Rendering.docx" ويقع في دليل المستند المحدد.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تكوين خيارات حفظ PDF

 لتضمين كل الخطوط في ملف PDF الناتج ، نحتاج إلى تكوين ملف`PdfSaveOptions` كائن مع`EmbedFullFonts` تعيين الخاصية على`true`. هذا يضمن أن كل الخطوط المستخدمة في الوثيقة متضمنة في ملف PDF الذي تم إنشاؤه.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
```

## الخطوة 4: احفظ المستند بصيغة PDF مع الخطوط المضمنة

 أخيرًا ، يمكننا حفظ المستند كملف PDF مع الخطوط المضمنة. حدد اسم ملف الإخراج ، و`saveOptions` كائن قمنا بتكوينه في الخطوة السابقة.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
```

هذا كل شيء! لقد نجحت في دمج جميع الخطوط في مستند وإنشاء ملف PDF مع الخطوط المضمنة باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لـ Embedded All Fonts باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// سيتم تضمين ملف PDF الناتج مع جميع الخطوط الموجودة في المستند.
	PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbeddedFontsInPdf.pdf", saveOptions);
  
```

## خاتمة

في هذا البرنامج التعليمي ، قمنا بتغطية العملية خطوة بخطوة لاستخدام ميزة Embedded All Fonts في Aspose.Words for .NET. لقد تعلمنا كيفية تحميل مستند ، وتكوين خيارات حفظ PDF ، وحفظ المستند كملف PDF مع الخطوط المضمنة. باتباع هذا الدليل ، يمكنك التأكد من أن مستندات PDF الخاصة بك تحتوي على جميع الخطوط الضرورية المضمنة ، مما يوفر عرضًا متسقًا ودقيقًا عبر الأجهزة والأنظمة الأساسية المختلفة.
