---
title: الحصول على قائمة الخطوط المتاحة
linktitle: الحصول على قائمة الخطوط المتاحة
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية الحصول على قائمة الخطوط المتوفرة في Aspose.Words for .NET.
type: docs
weight: 10
url: /es/net/working-with-fonts/get-list-of-available-fonts/
---
في هذا البرنامج التعليمي ، سنشرح كيفية الحصول على قائمة الخطوط المتوفرة في Aspose.Words for .NET. تتيح لك قائمة الخطوط المتوفرة معرفة الخطوط التي يمكنك استخدامها في مستنداتك. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

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

## الخطوة 2: تكوين مصادر الخطوط
 بعد ذلك ، سننشئ مثيلًا لـ`FontSettings` واحصل على مصادر الخطوط الحالية باستخدام امتداد`GetFontsSources()` طريقة. سنضيف أيضًا مصدر خط جديدًا عن طريق تحديد مجلد يحتوي على الخطوط.

```csharp
// تكوين مصادر الخط
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// أضف مصدر خط جديد
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## الخطوة 3: احصل على قائمة الخطوط المتاحة
 الآن سوف نتصفح الخطوط المتاحة باستخدام امتداد`GetAvailableFonts()` الطريقة على مصدر الخط الأول المحدث.

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


### عينة من التعليمات البرمجية المصدر للحصول على قائمة الخطوط المتاحة باستخدام Aspose.Words for .NET 

```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// أضف مصدر مجلد جديد والذي سيوجه Aspose.Words للبحث في المجلد التالي عن الخطوط.
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
في هذا البرنامج التعليمي ، رأينا كيفية الحصول على قائمة الخطوط المتوفرة في Aspose.Words for .NET. يتيح لك هذا معرفة الخطوط التي يمكنك استخدامها في مستنداتك. لا تتردد في استخدام هذه الميزة لاختيار الخطوط المناسبة لاحتياجاتك.