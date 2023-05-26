---
title: تعيين مجلد الخطوط
linktitle: تعيين مجلد الخطوط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين دليل الخطوط في Aspose.Words for .NET وتأكد من توفر الخطوط المستخدمة في مستنداتك.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-fonts-folder/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية تعيين دليل الخطوط في Aspose.Words for .NET. ستتعلم كيفية تحديد الدليل الذي يحتوي على الخطوط المستخدمة في مستند Word الخاص بك.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
ابدأ بتعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تعيين دليل الخطوط
 قم بإنشاء مثيل لـ`FontSettings` فئة واستخدام`SetFontsFolder` طريقة لتحديد الدليل الذي يحتوي على الخطوط. يستبدل`"Fonts"` باسم دليل الخطوط الفعلي.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## الخطوة 3: قم بتحميل المستند بإعدادات الخط
 استخدم ال`LoadOptions` فئة لتحديد إعدادات الخط في ملف`FontSettings` خيار. ثم استخدم ملف`Document` فئة لتحميل المستند باستخدام هذه الخيارات.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### نموذج التعليمات البرمجية المصدر لـ Set Fonts Folder باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## خاتمة
تهنئة ! أنت تعرف الآن كيفية تعيين دليل الخطوط في Aspose.Words for .NET. يمكنك استخدام هذه الميزة لضمان توفر الخطوط المستخدمة في وثيقتك ولضمان التناسق في عرض الخطوط.
