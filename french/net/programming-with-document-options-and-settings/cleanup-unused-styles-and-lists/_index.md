---
title: تنظيف الأنماط والقوائم غير المستخدمة
linktitle: تنظيف الأنماط والقوائم غير المستخدمة
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتنظيف الأنماط والقوائم غير المستخدمة في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /fr/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

في هذا البرنامج التعليمي ، سنرشدك عبر الكود المصدري C # لتنظيف الأنماط والقوائم غير المستخدمة باستخدام Aspose.Words for .NET. تتيح لك هذه الميزة إزالة الأنماط والقوائم غير المستخدمة في المستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي يحتوي على الأنماط والقوائم غير المستخدمة التي نريد تنظيفها. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: عد الأنماط والقوائم قبل التنظيف

قبل التنظيف ، سنقوم بحساب عدد الأنماط والقوائم الموجودة في المستند. استخدم الكود التالي لعرض العدادات:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

توضح هذه التعليمات عدد الأنماط والقوائم الموجودة في المستند قبل التنظيف.

## الخطوة 4: تنظيف الأنماط والقوائم غير المستخدمة

الآن دعنا ننظف الأنماط والقوائم غير المستخدمة من المستند. استخدم الكود التالي لإجراء التنظيف:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 يقوم هذا الرمز بتنظيف الأنماط والقوائم غير المستخدمة من المستند باستخدام الخيارات المحددة. في هذا المثال ، قمنا بتمكين`UnusedStyles` خيار لإزالة الأنماط غير المستخدمة وتعطيل`UnusedLists` خيار الاحتفاظ بالقوائم حتى لو لم يتم استخدامها.

## الخطوة 5: عد الأنماط والقوائم بعد التنظيف

بعد إجراء التنظيف ، سنعد الأنماط والقوائم مرة أخرى للتحقق مما إذا كانت مطوية أم لا. استخدم الكود التالي لعرض العدادات الجديدة:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

توضح هذه التعليمات عدد الأنماط والقوائم المتبقية بعد التنظيف.

### مثال على شفرة المصدر لـ Cleanup Unused Styles And Lists باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// بالاقتران مع الأنماط المضمنة ، يحتوي المستند الآن على ثمانية أنماط.
	// يتم تمييز النمط المخصص على أنه "مستخدم" أثناء وجود أي نص داخل المستند
	// منسق بهذا النمط. هذا يعني أن الأنماط الأربعة التي أضفناها غير مستخدمة حاليًا.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//ينظف الأنماط والقوائم غير المستخدمة من المستند بناءً على خيارات التنظيف المحددة.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تنظيف الأنماط والقوائم غير المستخدمة من مستند باستخدام Aspose.Words for .NET. باتباع الدليل المفصل خطوة بخطوة المتوفر في هذا البرنامج التعليمي ، يمكنك بسهولة تطبيق هذه الميزة على المستندات الخاصة بك.

