---
title: إعدادات الخط المثيل الافتراضي
linktitle: إعدادات الخط المثيل الافتراضي
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: في هذا البرنامج التعليمي، تعرف على كيفية تكوين إعدادات الخط الافتراضية في مستند Word باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/working-with-fonts/font-settings-default-instance/
---

سنرشدك في هذا البرنامج التعليمي إلى كيفية تكوين إعدادات الخط الافتراضية في مستند Word باستخدام مكتبة Aspose.Words لـ .NET. تسمح لك إعدادات الخط الافتراضية بتحديد مصادر الخطوط المستخدمة عند تحميل المستندات وعرضها. سنأخذك خطوة بخطوة لمساعدتك على فهم التعليمات البرمجية وتنفيذها في مشروع .NET الخاص بك.

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

## الخطوة 2: تكوين إعدادات الخط الافتراضية
 بعد ذلك، سنقوم بإنشاء مثيل لـ`FontSettings` استخدام`FontSettings.DefaultInstance`، ثم سنحدد مصادر الخطوط المستخدمة عند تحميل المستندات وعرضها. في هذا المثال، نستخدم مصدر خط النظام ومصدر خط المجلد.

```csharp
// تكوين إعدادات الخط الافتراضية
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## الخطوة 3: تحميل المستند بإعدادات الخط
 الآن سنقوم بتحميل المستند باستخدام`LoadOptions` وتحديد إعدادات الخط المراد استخدامه.

```csharp
// قم بتحميل المستند بإعدادات الخط
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### نموذج التعليمات البرمجية المصدر للمثيل الافتراضي لإعدادات الخط باستخدام Aspose.Words لـ .NET 
```csharp

// المسار إلى دليل المستندات الخاص بك
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
في هذا البرنامج التعليمي، رأينا كيفية تكوين إعدادات الخط الافتراضية في مستند Word باستخدام Aspose.Words for .NET. من خلال تحديد مصادر الخطوط المستخدمة عند تحميل المستندات وعرضها، يمكنك التحكم في مظهر الخطوط في مستنداتك. لا تتردد في استخدام هذه الميزة لتخصيص إعدادات الخط في مشاريعك.

### الأسئلة الشائعة

#### س: كيف يمكنني ضبط الخط الافتراضي في Aspose.Words؟

 ج: لتعيين الخط الافتراضي في Aspose.Words، يمكنك استخدام`FontSettings` الطبقة و`DefaultFontName` الخاصية التي تحدد اسم الخط المطلوب.

#### س: هل يمكنني تحديد حجم الخط الافتراضي في Aspose.Words؟

 ج: نعم، يمكنك تحديد حجم الخط الافتراضي في Aspose.Words باستخدام الملف`DefaultFontSize` ملكية`FontSettings` فصل. يمكنك ضبط حجم النقطة المطلوبة.

#### س: هل من الممكن ضبط لون الخط الافتراضي في Aspose.Words؟

 ج: نعم، يمكنك ضبط لون الخط الافتراضي في Aspose.Words باستخدام`DefaultColor` ملكية`FontSettings` فصل. يمكنك تحديد اللون باستخدام قيم RGB أو الأسماء المحددة مسبقًا.

#### س: هل تنطبق إعدادات الخط الافتراضية على كافة المستندات؟

ج: نعم، تنطبق إعدادات الخط الافتراضية على كافة المستندات التي تم إنشاؤها أو تحريرها في Aspose.Words، ما لم يتم تعيين إعدادات محددة لمستند فردي.