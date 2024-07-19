---
title: احصل على قائمة الخطوط المتاحة
linktitle: احصل على قائمة الخطوط المتاحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: في هذا البرنامج التعليمي، تعرف على كيفية الحصول على قائمة الخطوط المتوفرة في Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/get-list-of-available-fonts/
---
سنشرح في هذا البرنامج التعليمي كيفية الحصول على قائمة الخطوط المتوفرة في Aspose.Words لـ .NET. تتيح لك قائمة الخطوط المتوفرة معرفة الخطوط التي يمكنك استخدامها في مستنداتك. سنأخذك خطوة بخطوة لمساعدتك على فهم التعليمات البرمجية وتنفيذها في مشروع .NET الخاص بك.

## المتطلبات الأساسية
قبل البدء، تأكد من أن لديك العناصر التالية:
- معرفة عملية بلغة البرمجة C#
- تم تثبيت مكتبة Aspose.Words الخاصة بـ .NET في مشروعك

## الخطوة 1: تحديد دليل المستند
 أولاً، تحتاج إلى تعيين مسار الدليل إلى موقع مستند Word الخاص بك. يستبدل`"YOUR DOCUMENT DIRECTORY"` في الكود بالمسار المناسب

```csharp
// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تكوين مصادر الخطوط
 بعد ذلك، سنقوم بإنشاء مثيل لـ`FontSettings` والحصول على مصادر الخطوط الموجودة باستخدام`GetFontsSources()` طريقة. سنقوم أيضًا بإضافة مصدر خط جديد عن طريق تحديد مجلد يحتوي على الخطوط.

```csharp
// تكوين مصادر الخطوط
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// إضافة مصدر خط جديد
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## الخطوة 3: احصل على قائمة الخطوط المتاحة
 الآن سوف نقوم بتصفح الخطوط المتاحة باستخدام`GetAvailableFonts()` الطريقة على مصدر الخط المحدث الأول.

```csharp
// الحصول على قائمة الخطوط المتاحة
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### نموذج التعليمات البرمجية المصدر للحصول على قائمة الخطوط المتاحة باستخدام Aspose.Words لـ .NET 

```csharp

// المسار إلى دليل المستندات الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// قم بإضافة مصدر مجلد جديد والذي سيوجه Aspose.Words للبحث في المجلد التالي عن الخطوط.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// أضف المجلد المخصص الذي يحتوي على خطوطنا إلى قائمة مصادر الخطوط الموجودة.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## خاتمة
في هذا البرنامج التعليمي، رأينا كيفية الحصول على قائمة الخطوط المتوفرة في Aspose.Words لـ .NET. يتيح لك ذلك معرفة الخطوط التي يمكنك استخدامها في مستنداتك. لا تتردد في استخدام هذه الميزة لاختيار الخطوط المناسبة لاحتياجاتك.

### الأسئلة الشائعة

#### س: كيف يمكنني استرداد قائمة الخطوط المتوفرة في Aspose.Words؟

 ج: لاسترداد قائمة الخطوط المتوفرة في Aspose.Words، يمكنك استخدام الملف`FontsProvider` الطبقة و`GetAvailableFonts` طريقة. ستعيد هذه الطريقة قائمة بجميع الخطوط المثبتة على نظامك.

#### س: هل يمكنني تصفية قائمة الخطوط المتاحة حسب معايير معينة في Aspose.Words؟

ج: نعم، يمكنك تصفية قائمة الخطوط المتوفرة في Aspose.Words باستخدام معايير محددة. على سبيل المثال، يمكنك تصفية الخطوط حسب العائلة أو النمط أو اللغة.

#### س: كيف يمكنني استخدام قائمة الخطوط المتوفرة في مستندات Word الخاصة بي؟

 ج: لاستخدام قائمة الخطوط المتوفرة في مستندات Word الخاصة بك، يمكنك تصفح القائمة وتحديد الخطوط المناسبة باستخدام طرق وخصائص`FontSettings` فئة في Aspose.Words.