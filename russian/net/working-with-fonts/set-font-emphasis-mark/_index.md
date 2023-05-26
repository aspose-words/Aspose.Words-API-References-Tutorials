---
title: قم بتعيين علامة توكيد الخط
linktitle: قم بتعيين علامة توكيد الخط
second_title: Aspose.Words لمراجع .NET API
description: تعرف على كيفية تعيين نمط تأكيد الخط في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-font-emphasis-mark/
---

في هذا البرنامج التعليمي ، سنوضح لك كيفية تعيين نمط تأكيد الخط في مستند Word باستخدام Aspose.Words for .NET. يستخدم التركيز على الخط لتمييز بعض الكلمات أو العبارات في النص.

## المتطلبات الأساسية
قبل أن تبدأ ، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C #
- تم تثبيت مكتبة Aspose.Words لـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
ابدأ بتعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء وتخصيص المستند
 قم بإنشاء مثيل لـ`Document` فئة وما يرتبط بها`DocumentBuilder` لبناء محتوى الوثيقة. استخدم ال`Font.EmphasisMark`لتعيين نمط تأكيد الخط إلى`EmphasisMark.UnderSolidCircle` . ثم استخدم ملف`Write` و`Writeln` طرق`DocumentBuilder` لإضافة نص مع التركيز على الخط المحدد.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## الخطوة 3: احفظ المستند
 احفظ المستند باستخدام ملف`Save` طريقة`Document` بالمسار واسم الملف المناسبين.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### نموذج التعليمات البرمجية المصدر لـ Set Font Emphasis Mark باستخدام Aspose.Words for .NET 

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمت كيفية تعيين نمط تأكيد الخط في مستند Word باستخدام Aspose.Words for .NET. جرب أنماطًا مختلفة من التركيز واستخدم هذه الميزة لتمييز الكلمات أو العبارات في مستنداتك.
