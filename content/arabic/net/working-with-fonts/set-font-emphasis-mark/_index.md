---
title: تعيين علامة التأكيد على الخط
linktitle: تعيين علامة التأكيد على الخط
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية تعيين نمط تركيز الخط في مستند Word باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/set-font-emphasis-mark/
---

سنوضح لك في هذا البرنامج التعليمي كيفية تعيين نمط تركيز الخط في مستند Word باستخدام Aspose.Words for .NET. يتم استخدام التركيز على الخط لتسليط الضوء على كلمات أو عبارات معينة في النص.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
ابدأ بتعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: إنشاء وتخصيص المستند
 إنشاء مثيل لـ`Document` الطبقة وما يرتبط بها`DocumentBuilder` لبناء محتوى الوثيقة. استخدم ال`Font.EmphasisMark` خاصية لتعيين نمط التركيز على الخط`EmphasisMark.UnderSolidCircle` . ثم استخدم`Write` و`Writeln` أساليب`DocumentBuilder` لإضافة نص مع التركيز على الخط المحدد.

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
 احفظ المستند باستخدام`Save` طريقة`Document` بالمسار المناسب واسم الملف.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### نموذج التعليمات البرمجية المصدر لعلامة Set Font Enphasis Mark باستخدام Aspose.Words لـ .NET 

```csharp
// المسار إلى دليل المستندات الخاص بك
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
في هذا البرنامج التعليمي، تعلمت كيفية تعيين نمط تركيز الخط في مستند Word باستخدام Aspose.Words لـ .NET. قم بتجربة أنماط مختلفة من التركيز واستخدم هذه الميزة لتمييز الكلمات أو العبارات في مستنداتك.

### الأسئلة الشائعة

#### س: كيف يمكنني إضافة علامات التشكيل إلى خط معين في مستند Word باستخدام Aspose.Words؟

ج: لإضافة علامات التشكيل إلى خط معين في مستند Word باستخدام Aspose.Words، يمكنك استخدام واجهة برمجة التطبيقات (API) للانتقال إلى الخط المطلوب وتطبيق علامات التشكيل المناسبة. سيؤدي هذا إلى إضافة علامات التشكيل إلى النص بالخط المحدد.

#### س: هل من الممكن تغيير نمط علامات التشكيل في مستند Word باستخدام Aspose.Words؟

ج: نعم، باستخدام Aspose.Words يمكنك تغيير نمط علامات التشكيل في مستند Word. تتيح لك واجهة برمجة التطبيقات (API) ضبط خصائص النمط مثل اللون والحجم ونوع الخط وما إلى ذلك، لتخصيص مظهر علامات التمييز.

#### س: كيف يمكنني إزالة كافة علامات التشكيل من مستند Word باستخدام Aspose.Words؟

ج: لإزالة كافة علامات التشكيل من مستند Word باستخدام Aspose.Words، يمكنك استخدام واجهة برمجة التطبيقات (API) لتصفح المستند واكتشاف علامات التشكيل الموجودة وإزالتها باستخدام الطرق المناسبة. سيؤدي هذا إلى إزالة كافة علامات التركيز من المستند.

#### س: هل يمكنني إضافة علامات التشكيل إلى جزء معين من النص في مستند Word؟

ج: نعم، يمكنك إضافة علامات التشكيل إلى جزء معين من النص في مستند Word باستخدام Aspose.Words. يمكنك تحديد النطاق المطلوب من النص باستخدام واجهة برمجة التطبيقات (API) وإضافة علامات التركيز المناسبة إلى ذلك الجزء من النص.

#### س: هل يمكن تخصيص علامات التشكيل حسب احتياجاتي؟

ج: نعم، يمكن تخصيص علامات التشكيل حسب احتياجاتك باستخدام Aspose.Words. يمكنك ضبط خصائص نمط علامات التشكيل، مثل اللون والحجم ونوع الخط والمزيد، لتتوافق مع تفضيلات التنسيق الخاصة بك.