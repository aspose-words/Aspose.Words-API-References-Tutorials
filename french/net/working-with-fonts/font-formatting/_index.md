---
title: تنسيق الخط
linktitle: تنسيق الخط
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية تنسيق الخط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/working-with-fonts/font-formatting/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تنسيق الخط في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. يتيح لك تنسيق الخط تخصيص مظهر النص ، بما في ذلك الحجم والغامق واللون والخط والتسطير والمزيد. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

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

## الخطوة 2: إنشاء مستند جديد ومولد مستندات
 بعد ذلك ، سننشئ مستندًا جديدًا عن طريق إنشاء مثيل لملف`Document` class ومنشئ المستندات عن طريق إنشاء مثيل لملف`DocumentBuilder` فصل.

```csharp
// قم بإنشاء مستند جديد
Document doc = new Document();

// قم بإنشاء منشئ المستندات
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: تكوين تنسيق الخط
 الآن سوف نصل إلى`Font` كائن من منشئ المستند وتكوين خصائص تنسيق الخط مثل الحجم ، والجريء ، واللون ، والخط ، والتسطير ، وما إلى ذلك.

```csharp
// الوصول إلى الخط
Font font = builder.Font;

// تكوين تنسيق الخط
font.Size = 16;
font. Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
```

## الخطوة 4: أضف نصًا إلى المستند
بعد ذلك ، سنستخدم منشئ المستندات لإضافة بعض النص المنسق إلى المستند.

```csharp
// أضف نصًا إلى المستند
builder.Write("Example text.");
```

## الخطوة 5: احفظ المستند
أخيرًا ، سنحفظ المستند الذي يحتوي على تنسيق الخط.

```csharp
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

### نموذج التعليمات البرمجية المصدر لتنسيق الخط باستخدام Aspose.Words for .NET 
```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Font font = builder.Font;
font.Size = 16;
font.Bold = true;
font.Color = Color.Blue;
font.Name = "Arial";
font.Underline = Underline.Dash;
builder.Write("Sample text.");
doc.Save(dataDir + "WorkingWithFonts.FontFormatting.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية تنسيق الخط في مستند Word باستخدام Aspose.Words for .NET. يسمح لك تنسيق الخط بتخصيص مظهر النص في مستنداتك. لا تتردد في استخدام هذه الميزة لإنشاء مستندات جذابة واحترافية.