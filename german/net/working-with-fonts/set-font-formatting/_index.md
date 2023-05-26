---
title: قم بتعيين تنسيق الخط
linktitle: قم بتعيين تنسيق الخط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين تنسيق الخط في مستند Word باستخدام Aspose.Words for .NET وإنشاء مستندات جذابة.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-font-formatting/
---
في هذا البرنامج التعليمي ، سنوضح لك كيفية تعيين تنسيق الخط في مستند Word باستخدام Aspose.Words for .NET. سوف تتعلم كيفية تطبيق أنماط مثل الغامق واللون والمائل والخط والحجم والتباعد والتسطير.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
ابدأ بتعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بإنشاء وتنسيق المستند
 قم بإنشاء مثيل لـ`Document` الطبقة و`DocumentBuilder` فئة لبناء الوثيقة. استخدم ال`Font` ممتلكات`DocumentBuilder` للوصول إلى خصائص تنسيق الخط.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font. Bold = true;
font.Color = Color.DarkBlue;
font. Italic = true;
font.Name = "Arial";
font.Size = 24;
font. Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nicely formatted string.");
```

## الخطوة 3: احفظ المستند
 استخدم ال`Save` طريقة لحفظ المستند مع تنسيق الخط المطبق. يستبدل`"WorkingWithFonts.SetFontFormatting.docx"` مع اسم الملف المطلوب.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");
```

### نموذج التعليمات البرمجية المصدر لـ Set Font Formatting باستخدام Aspose.Words for .NET 
```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Bold = true;
font.Color = Color.DarkBlue;
font.Italic = true;
font.Name = "Arial";
font.Size = 24;
font.Spacing = 5;
font.Underline = Underline.Double;
builder.Writeln("I'm a very nice formatted string.");
doc.Save(dataDir + "WorkingWithFonts.SetFontFormatting.docx");

```

## خاتمة
تهنئة ! أنت تعرف الآن كيفية تعيين تنسيق الخط في مستند Word باستخدام Aspose.Words for .NET. يمكنك استكشاف المزيد من خيارات تنسيق الخط وإنشاء مستندات Word مخصصة وجذابة.
