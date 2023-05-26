---
title: مثال مصدر خط Steam
linktitle: مثال مصدر خط Steam
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية استخدام مصدر خط تدفق الموارد لتحميل الخطوط المخصصة في Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/resource-steam-font-source-example/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية استخدام مصدر خط تدفق الموارد مع Aspose.Words for .NET. يتيح لك مصدر الخط هذا تحميل الخطوط من تدفق الموارد ، والذي يمكن أن يكون مفيدًا عندما تريد دمج الخطوط المخصصة في تطبيقك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
 أولاً ، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل المستند وتعيين مصدر خط تدفق الموارد
 بعد ذلك ، سنقوم بتحميل المستند باستخدام ملف`Document` فئة وتعيين مصدر خط تدفق الموارد باستخدام`FontSettings.DefaultInstance.SetFontsSources()` فصل. سيسمح هذا لـ Aspose.Words بالعثور على الخطوط في تدفق الموارد.

```csharp
// تحميل المستند وتعيين مصدر خط تدفق الموارد
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{ new SystemFontSource(), new ResourceSteamFontSource() });
```

## الخطوة 3: احفظ المستند
أخيرًا ، سنحفظ المستند. سيتم تحميل الخطوط من تدفق الموارد المحدد وتضمينها في المستند.

```csharp
// احفظ المستند
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### نموذج رمز مصدر لمثال مصدر خط Resource Steam باستخدام Aspose.Words for .NET 

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{ new SystemFontSource(), new ResourceSteamFontSource() });
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمت كيفية استخدام Resource Flow Font Source مع Aspose.Words for .NET. تتيح لك هذه الميزة تحميل الخطوط من موجز الموارد ، وهو أمر مفيد عندما تريد تضمين الخطوط المخصصة في مستنداتك. جرب خطوطًا مختلفة واستكشف الإمكانيات التي توفرها Aspose.Words لإدارة الخطوط.
