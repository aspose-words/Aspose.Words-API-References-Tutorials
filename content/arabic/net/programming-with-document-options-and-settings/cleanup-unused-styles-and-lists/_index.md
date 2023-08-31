---
title: تنظيف الأنماط والقوائم غير المستخدمة
linktitle: تنظيف الأنماط والقوائم غير المستخدمة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتنظيف الأنماط والقوائم غير المستخدمة في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-document-options-and-settings/cleanup-unused-styles-and-lists/
---

في هذا البرنامج التعليمي، سنرشدك عبر التعليمات البرمجية المصدر لـ C# لتنظيف الأنماط والقوائم غير المستخدمة باستخدام Aspose.Words for .NET. تسمح لك هذه الميزة بإزالة الأنماط والقوائم غير المستخدمة في المستند.

## الخطوة 1: إعداد المشروع

للبدء، قم بإنشاء مشروع C# جديد في بيئة التطوير المتكاملة (IDE) المفضلة لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة 2: تحميل الوثيقة

في هذه الخطوة، سنقوم بتحميل مستند Word الذي يحتوي على الأنماط والقوائم غير المستخدمة التي نريد تنظيفها. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Unused styles.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` بالمسار الفعلي للدليل الذي يوجد به المستند الخاص بك.

## الخطوة 3: عد الأنماط والقوائم قبل التنظيف

قبل التنظيف، سنقوم بإحصاء عدد الأنماط والقوائم الموجودة في المستند. استخدم الكود التالي لعرض العدادات:

```csharp
Console.WriteLine($"Number of styles before cleaning: {doc.Styles.Count}\n" +
$"Number of lists before cleaning: {doc.Lists.Count}");
```

توضح هذه الإرشادات عدد الأنماط والقوائم الموجودة في المستند قبل التنظيف.

## الخطوة 4: تنظيف الأنماط والقوائم غير المستخدمة

لنقم الآن بتنظيف الأنماط والقوائم غير المستخدمة من المستند. استخدم الكود التالي لإجراء عملية التنظيف:

```csharp
CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
doc. Cleanup(cleanupOptions);
```

 يقوم هذا الرمز بتنظيف الأنماط والقوائم غير المستخدمة من المستند باستخدام الخيارات المحددة. في هذا المثال، قمنا بتمكين`UnusedStyles` خيار إزالة الأنماط غير المستخدمة وتعطيل`UnusedLists` خيار الاحتفاظ بالقوائم حتى لو لم يتم استخدامها.

## الخطوة 5: عد الأنماط والقوائم بعد التنظيف

بعد إجراء عملية التنظيف، سنقوم بعد الأنماط والقوائم مرة أخرى للتحقق مما إذا كانت مطوية أم لا. استخدم الكود التالي لعرض العدادات الجديدة:

```csharp
Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
				  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
```

توضح هذه التعليمات عدد الأنماط والقوائم المتبقية بعد التنظيف.

### مثال على التعليمات البرمجية المصدر لتنظيف الأنماط والقوائم غير المستخدمة باستخدام Aspose.Words لـ .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Unused styles.docx");

	// بالإضافة إلى الأنماط المضمنة، أصبح المستند الآن يحتوي على ثمانية أنماط.
	// يتم وضع علامة "مستخدم" على النمط المخصص أثناء وجود أي نص داخل المستند
	// تم تنسيقه بهذا النمط. وهذا يعني أن الأنماط الأربعة التي أضفناها غير مستخدمة حاليًا.
	Console.WriteLine($"Count of styles before Cleanup: {doc.Styles.Count}\n" +
					  $"Count of lists before Cleanup: {doc.Lists.Count}");

	//ينظف الأنماط والقوائم غير المستخدمة من المستند اعتمادًا على خيارات التنظيف المحددة.
	CleanupOptions cleanupOptions = new CleanupOptions { UnusedLists = false, UnusedStyles = true };
	doc.Cleanup(cleanupOptions);

	Console.WriteLine($"Count of styles after Cleanup was decreased: {doc.Styles.Count}\n" +
					  $"Count of lists after Cleanup is the same: {doc.Lists.Count}");

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupUnusedStylesAndLists.docx");
    
```

 تأكد من تحديد مسار المستند الصحيح في ملف`dataDir` عامل.

لقد تعلمت الآن كيفية تنظيف الأنماط والقوائم غير المستخدمة من مستند باستخدام Aspose.Words for .NET. باتباع الدليل التفصيلي المقدم في هذا البرنامج التعليمي، يمكنك بسهولة تطبيق هذه الميزة على مستنداتك الخاصة.

