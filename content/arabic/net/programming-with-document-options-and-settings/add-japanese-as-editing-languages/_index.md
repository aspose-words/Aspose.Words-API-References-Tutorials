---
title: إضافة اليابانية كلغات التحرير
linktitle: إضافة اليابانية كلغات التحرير
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لإضافة اللغة اليابانية كلغة تحرير باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

في هذا البرنامج التعليمي، سنأخذك خطوة بخطوة لفهم وظيفة إضافة اللغة اليابانية كلغة تحرير باستخدام Aspose.Words for .NET وتنفيذها. تتيح لك هذه الميزة ضبط تفضيلات اللغة عند تحميل مستند وإضافة اللغة اليابانية كلغة تحرير.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي لا يحتوي على لغة تحرير افتراضية والذي نريد إضافة اللغة اليابانية إليه. استخدم الكود التالي لتحميل المستند:

```csharp
LoadOptions loadOptions = new LoadOptions();

// قم بتعيين تفضيلات اللغة التي سيتم استخدامها عند تحميل المستند.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## الخطوة 3: التحقق من اللغة الافتراضية

بعد تحميل المستند، سوف نتحقق مما إذا تم ضبط لغة التحرير الافتراضية بشكل صحيح على اللغة اليابانية. استخدم الكود التالي للحصول على معرف لغة الشرق الأقصى:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

يتحقق الرمز مما إذا كان معرف لغة الشرق الأقصى يتطابق مع معرف اللغة اليابانية. ووفقا للنتيجة، فإنه يعرض الرسالة المقابلة.

### مثال على التعليمات البرمجية المصدر لإضافة اللغة اليابانية كلغات تحرير باستخدام Aspose.Words لـ .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// قم بتعيين تفضيلات اللغة التي سيتم استخدامها عند تحميل المستند.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```

