---
title: تعيين مجلدات الخطوط
linktitle: تعيين مجلدات الخطوط
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإعداد مجلدات الخطوط عند تقديم مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/working-with-fonts/set-fonts-folders/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين مجلدات الخطوط عند عرض مستند باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. بنهاية هذا البرنامج التعليمي ، ستعرف كيفية تحديد مجلدات الخطوط لاستخدامها عند عرض مستنداتك باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ المستند الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: تعيين مصادر الخط
 ثم يمكنك ضبط مصادر الخط باستخدام امتداد`FontSettings.DefaultInstance` الطبقة و`SetFontsSources()` طريقة. في هذا المثال ، نستخدم كلاً من مصدر خط النظام ومصدر خط مجلد مخصص. تأكد من ضبط المسار إلى مجلد الخطوط المخصصة وفقًا لاحتياجاتك.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## الخطوة 3: قم بتحميل المستند للعرض
 يمكنك الآن تحميل المستند لتقديمه باستخدام امتداد`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## الخطوة 4: احفظ المستند المقدم
 أخيرًا ، يمكنك حفظ المستند الذي تم تقديمه في ملف باستخدام امتداد`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

### نموذج التعليمات البرمجية المصدر لـ Set Fonts Folders باستخدام Aspose.Words for .NET 
```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
	{
		new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true)
	});
	Document doc = new Document(dataDir + "Rendering.docx");
	doc.Save(dataDir + "WorkingWithFonts.SetFontsFolders.pdf");
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين مجلدات الخطوط عند عرض مستند باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة تحديد مصادر الخطوط لاستخدامها عند عرض مستنداتك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة للعمل مع الخطوط في مستنداتك. باستخدام هذه المعرفة ، يمكنك التحكم في مصادر الخطوط المستخدمة عند تقديم مستنداتك لاحتياجاتك الخاصة وتخصيصها.