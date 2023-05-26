---
title: تعيين اللغة الروسية كلغة تحرير افتراضية
linktitle: تعيين اللغة الروسية كلغة تحرير افتراضية
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتعيين اللغة الروسية كلغة تحرير افتراضية لمستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتعيين اللغة الروسية كلغة تحرير افتراضية باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة ضبط اللغة الافتراضية عند تحميل مستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد تعيين اللغة الروسية له كلغة التحرير الافتراضية. استخدم الكود التالي لتحميل المستند:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: التحقق من اللغة الافتراضية

بعد تحميل المستند ، سنتحقق مما إذا كانت اللغة الافتراضية قد تم ضبطها بشكل صحيح على الروسية. استخدم الكود التالي للحصول على معرف اللغة الافتراضي:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

يتحقق الكود مما إذا كان معرف اللغة يطابق معرف اللغة الروسية. وفقًا للنتيجة ، فإنه يعرض رسالة مقابلة.

### مثال على شفرة المصدر لتعيين الروسية كلغة تحرير افتراضية باستخدام Aspose.Words for .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تعيين اللغة الروسية كلغة تحرير افتراضية لمستند باستخدام Aspose.Words for .NET. باتباع دليل الخطوة