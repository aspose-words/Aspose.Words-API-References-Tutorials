---
title: المثيل الافتراضي لإعدادات الخط
linktitle: المثيل الافتراضي لإعدادات الخط
second_title: Aspose.Words لمراجع .NET API
description: في هذا البرنامج التعليمي ، تعرف على كيفية تكوين إعدادات الخط الافتراضية في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /zh/net/working-with-fonts/font-settings-default-instance/
---

في هذا البرنامج التعليمي ، سنرشدك إلى كيفية تكوين إعدادات الخط الافتراضية في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. تسمح لك إعدادات الخط الافتراضية بتحديد مصادر الخطوط المستخدمة عند تحميل المستندات وعرضها. سنأخذك خطوة بخطوة لمساعدتك على فهم وتنفيذ الكود في مشروع .NET الخاص بك.

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

## الخطوة 2: تكوين إعدادات الخط الافتراضية
 بعد ذلك ، سننشئ مثيلًا لـ`FontSettings` استخدام`FontSettings.DefaultInstance`، ثم سنحدد مصادر الخطوط المستخدمة عند تحميل المستندات وعرضها. في هذا المثال ، نستخدم مصدر خط نظام ومصدر خط مجلد.

```csharp
// تكوين إعدادات الخط الافتراضية
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## الخطوة 3: تحميل المستند مع إعدادات الخط
 الآن سنقوم بتحميل المستند باستخدام`LoadOptions` وتحديد إعدادات الخط المراد استخدامها.

```csharp
// قم بتحميل المستند بإعدادات الخط
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### نموذج كود مصدر لإعدادات الخط الافتراضي باستخدام Aspose.Words for .NET 
```csharp

// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## خاتمة
في هذا البرنامج التعليمي ، رأينا كيفية تكوين إعدادات الخط الافتراضية في مستند Word باستخدام Aspose.Words for .NET. من خلال تحديد مصادر الخطوط المستخدمة عند تحميل المستندات وعرضها ، يمكنك التحكم في مظهر الخطوط في مستنداتك. لا تتردد في استخدام هذه الميزة لتخصيص إعدادات الخط في مشاريعك.