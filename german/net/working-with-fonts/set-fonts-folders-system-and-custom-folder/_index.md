---
title: تعيين نظام مجلدات الخطوط والمجلد المخصص
linktitle: تعيين نظام مجلدات الخطوط والمجلد المخصص
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإعداد النظام ومجلدات الخطوط المخصصة عند تقديم مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين مجلدات خطوط النظام ومجلد مخصص عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد مجلدات خطوط متعددة ، بما في ذلك مجلد النظام والمجلد المخصص ، لاستخدامها عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند للعرض
 ثم يمكنك تحميل المستند لتقديمه باستخدام امتداد`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 3: تعيين مجلدات الخط المخصصة والنظام
 يمكنك الآن تعيين مجلدات خطوط النظام ومجلد مخصص باستخدام ملف`FontSettings` الطبقة و`SetFontsSources()` طريقة. أولاً ، تحتاج إلى استرداد قائمة مصادر الخطوط المعتمدة على البيئة التي تستخدم`GetFontsSources()` وتخزينه في قائمة. ثم يمكنك إنشاء مثيل جديد من`FolderFontSource`تحديد المسار إلى المجلد المخصص الذي يحتوي على الخطوط الخاصة بك. أضف هذا المثيل إلى قائمة مصادر الخطوط الموجودة. أخيرًا ، استخدم`SetFontsSources()` لتحديث مصادر الخطوط بالقائمة الجديدة.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## الخطوة 4: تطبيق إعدادات الخط
 بعد ذلك ، تحتاج إلى تطبيق إعدادات الخط على المستند الخاص بك باستخدام ملف`FontSettings` ممتلكات`Document` فصل.

```csharp
doc.FontSettings = fontSettings;
```

## الخطوة 5: احفظ المستند المقدم
أخيرًا ، يمكنك حفظ المستند الذي تم تقديمه في ملف بواسطة

   باستخدام`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### عينة من التعليمات البرمجية المصدر لـ Set Fonts Folders System والمجلد المخصص باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// استرجع مصفوفة مصادر الخطوط المعتمدة على البيئة والتي يتم البحث عنها افتراضيًا.
	// على سبيل المثال سيحتوي هذا على مصدر "Windows \ Fonts \" على أجهزة Windows.
	// نضيف هذه المجموعة إلى قائمة جديدة لتسهيل إضافة أو إزالة مدخلات الخط.
	List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
	// أضف مصدر مجلد جديد والذي سيوجه Aspose.Words للبحث في المجلد التالي عن الخطوط.
	FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
	// أضف المجلد المخصص الذي يحتوي على خطوطنا إلى قائمة مصادر الخطوط الموجودة.
	fontSources.Add(folderFontSource);
	FontSourceBase[] updatedFontSources = fontSources.ToArray();
	fontSettings.SetFontsSources(updatedFontSources);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين مجلدات خطوط النظام ومجلد مخصص عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تحديد مجلدات خطوط متعددة ، بما في ذلك مجلد النظام والمجلد المخصص ، لاستخدامهما عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة للعمل مع الخطوط في مستنداتك. باستخدام هذه المعرفة ، يمكنك التحكم في مصادر الخطوط المستخدمة عند تقديم مستنداتك لاحتياجاتك الخاصة وتخصيصها.