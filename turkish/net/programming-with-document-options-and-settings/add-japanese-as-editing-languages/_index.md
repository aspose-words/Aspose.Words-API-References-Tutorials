---
title: أضف اليابانية كلغات تحرير
linktitle: أضف اليابانية كلغات تحرير
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لإضافة اليابانية كلغة تحرير باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

في هذا البرنامج التعليمي ، سوف نأخذك خطوة بخطوة لفهم وتنفيذ وظيفة إضافة اللغة اليابانية كلغة تحرير باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة ضبط تفضيلات اللغة عند تحميل مستند وإضافة اليابانية كلغة تحرير.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي لا يحتوي على لغة تحرير افتراضية والتي نريد إضافة اللغة اليابانية إليها. استخدم الكود التالي لتحميل المستند:

```csharp
LoadOptions loadOptions = new LoadOptions();

// قم بتعيين تفضيلات اللغة التي سيتم استخدامها عند تحميل المستند.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## الخطوة 3: التحقق من اللغة الافتراضية

بعد تحميل المستند ، سنتحقق مما إذا كانت لغة التحرير الافتراضية قد تم ضبطها بشكل صحيح على اليابانية. استخدم الكود التالي للحصول على معرف لغة الشرق الأقصى:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

يتحقق الكود مما إذا كان معرف لغة الشرق الأقصى يطابق معرف اللغة اليابانية. وفقًا للنتيجة ، فإنه يعرض رسالة مقابلة.

### مثال على شفرة المصدر لإضافة اليابانية كلغات تحرير باستخدام Aspose.Words for .NET

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

