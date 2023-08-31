---
title: تعيين اللغة الروسية كلغة التحرير الافتراضية
linktitle: تعيين اللغة الروسية كلغة التحرير الافتراضية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتعيين اللغة الروسية كلغة التحرير الافتراضية للمستند باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتعيين اللغة الروسية كلغة التحرير الافتراضية مع Aspose.Words for .NET. تتيح لك هذه الميزة ضبط اللغة الافتراضية عند تحميل مستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي نريد تعيين اللغة الروسية كلغة التحرير الافتراضية له. استخدم الكود التالي لتحميل المستند:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: التحقق من اللغة الافتراضية

بعد تحميل المستند، سنتحقق مما إذا تم ضبط اللغة الافتراضية بشكل صحيح على اللغة الروسية. استخدم الكود التالي للحصول على معرف اللغة الافتراضي:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

يتحقق الرمز مما إذا كان معرف اللغة يطابق معرف اللغة الروسية. ووفقا للنتيجة، فإنه يعرض الرسالة المقابلة.

### مثال على التعليمات البرمجية المصدر لتعيين اللغة الروسية كلغة تحرير افتراضية باستخدام Aspose.Words لـ .NET

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

لقد تعلمت الآن كيفية تعيين اللغة الروسية كلغة التحرير الافتراضية للمستند باستخدام Aspose.Words لـ .NET. باتباع دليل الخطوة