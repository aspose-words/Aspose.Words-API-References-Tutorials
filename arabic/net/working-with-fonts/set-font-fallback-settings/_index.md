---
title: تعيين إعدادات الخط الاحتياطي
linktitle: تعيين إعدادات الخط الاحتياطي
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين إعدادات استبدال الخطوط في Aspose.Words for .NET وتخصيص استبدال الخط في مستندات Word.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-font-fallback-settings/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية تعيين إعدادات استبدال الخط في مستند Word باستخدام Aspose.Words for .NET. تسمح لك إعدادات استبدال الخط بتحديد الخطوط البديلة لاستخدامها عندما لا تكون الخطوط المحددة متاحة.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
ابدأ بتعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تحميل إعدادات استبدال الخط
 قم بإنشاء مثيل لـ`FontSettings` فئة واستخدام`Load`طريقة لتحميل إعدادات تجاوز الخط من ملف XML. يجب أن يحتوي ملف XML المحدد على قواعد استبدال الخط المراد استخدامها.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font Fallback Rules.xml");
```

## الخطوة 3: تطبيق إعدادات استبدال الخط
 إقران إعدادات استبدال الخط بالمستند من خلال تخصيصها للمستند`FontSettings` ملكية.

```csharp
doc.FontSettings = fontSettings;
```

## الخطوة 4: احفظ المستند
 احفظ المستند باستخدام ملف`Save` طريقة`Document` بالمسار واسم الملف المناسبين.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Set Font Fallback Settings باستخدام Aspose.Words for .NET 
```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.FallbackSettings.Load(dataDir + "Font fallback rules.xml");
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontFallbackSettings.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمت كيفية تعيين إعدادات استبدال الخط في مستند Word باستخدام Aspose.Words for .NET. جرب قواعد مختلفة لاستبدال الخطوط للتأكد من تناسق وثيقتك ، حتى عندما لا تكون الخطوط المحددة متاحة.
