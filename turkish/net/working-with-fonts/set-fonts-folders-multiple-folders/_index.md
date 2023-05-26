---
title: تعيين مجلدات الخطوط متعددة المجلدات
linktitle: تعيين مجلدات الخطوط متعددة المجلدات
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتعيين مجلدات خطوط متعددة عند تقديم مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين مجلدات خطوط متعددة عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد مجلدات خطوط متعددة لاستخدامها عند عرض مستنداتك باستخدام Aspose.Words for .NET.

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

## الخطوة 3: تعيين مجلدات الخطوط
 الآن يمكنك تعيين مجلدات خطوط متعددة باستخدام ملف`FontSettings` الطبقة و`SetFontsFolders()` طريقة. يمكنك تحديد مسارات مجلدات الخطوط التي تريد استخدامها في مصفوفة. في هذا المثال ، حددنا مجلدين للخط: "C: \ MyFonts\"و" D: \ Misc \ Fonts\”。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## الخطوة 4: تطبيق إعدادات الخط
 بعد ذلك ، تحتاج إلى تطبيق إعدادات الخط على المستند الخاص بك باستخدام ملف`FontSettings` ممتلكات`Document` فصل.

```csharp
doc.FontSettings = fontSettings;
```

## الخطوة 5: احفظ المستند المقدم
 أخيرًا ، يمكنك حفظ المستند الذي تم تقديمه في ملف باستخدام امتداد`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### عينة من التعليمات البرمجية المصدر لـ Set Fonts Folders Multiple Folders باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Rendering.docx");
	FontSettings fontSettings = new FontSettings();
	// لاحظ أن هذا الإعداد سيتجاوز أي مصادر افتراضية للخطوط يتم البحث عنها افتراضيًا. الآن سيتم البحث عن هذه المجلدات فقط
	// الخطوط عند تقديم أو دمج الخطوط. لإضافة مصدر خط إضافي مع الاحتفاظ بمصادر خطوط النظام ، استخدم كلاً من FontSettings.GetFontSources و
	// FontSettings.SetFontSources بدلاً من ذلك.
	fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
	doc.FontSettings = fontSettings;
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين مجلدات خطوط متعددة عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تحديد مجلدات خطوط متعددة لاستخدامها عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة للعمل مع الخطوط في مستنداتك. باستخدام هذه المعرفة ، يمكنك التحكم في مصادر الخطوط المستخدمة عند تقديم مستنداتك لاحتياجاتك الخاصة وتخصيصها.