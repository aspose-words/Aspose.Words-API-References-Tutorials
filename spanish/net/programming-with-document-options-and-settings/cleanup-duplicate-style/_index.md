---
title: تنظيف النمط المكرر
linktitle: تنظيف النمط المكرر
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتنظيف الأنماط المكررة في مستند باستخدام Aspose.Words for .NET. تم تضمين كود المصدر الكامل.
type: docs
weight: 10
url: /es/net/programming-with-document-options-and-settings/cleanup-duplicate-style/
---

في هذا البرنامج التعليمي ، سنرشدك خلال التعليمات البرمجية المصدر C # خطوة بخطوة لتنظيف الأنماط المكررة باستخدام Aspose.Words for .NET. تساعد هذه الميزة في إزالة الأنماط المكررة من المستند.

## الخطوة 1: إعداد المشروع

للبدء ، قم بإنشاء مشروع C # جديد في IDE المفضل لديك. تأكد من الإشارة إلى مكتبة Aspose.Words for .NET في مشروعك.

## الخطوة الثانية: تحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي نريد تنظيفه. استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 يستبدل`"YOUR DOCUMENTS DIRECTORY"` مع المسار الفعلي للدليل حيث يوجد المستند الخاص بك.

## الخطوة 3: عد الأنماط قبل التنظيف

قبل متابعة التنظيف ، سنقوم بحساب عدد الأنماط الموجودة في المستند. استخدم الكود التالي لعرض عدد الأنماط:

```csharp
Console.WriteLine(doc.Styles.Count);
```

يعرض هذا البيان عدد الأنماط الموجودة في المستند.

## الخطوة 4: تنظيف الأنماط المكررة

لنقم الآن بتنظيف الأنماط المكررة من المستند. استخدم الكود التالي لإجراء التنظيف:

```csharp
CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
doc. Cleanup(options);
```

 يقوم هذا الرمز بتنظيف الأنماط المكررة من المستند باستخدام الخيارات المحددة. في هذا المثال ، قمنا بتمكين`DuplicateStyle` خيار لتنظيف الأنماط المكررة.

## الخطوة 5: عد الأنماط بعد التنظيف

بعد إجراء التنظيف ، سنحسب عدد الأنماط مرة أخرى للتحقق مما إذا كان قد انخفض. استخدم الكود التالي لعرض عدد الأنماط الجديدة:

```csharp
Console.WriteLine(doc.Styles.Count);
doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");
```

يعرض هذا البيان عدد الأنماط المتبقية بعد التنظيف.

### مثال على شفرة المصدر لـ Cleanup Duplicate Style باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// عدد الأنماط قبل التنظيف.
	Console.WriteLine(doc.Styles.Count);

	// ينظف الأنماط المكررة من المستند.
	CleanupOptions options = new CleanupOptions { DuplicateStyle = true };
	doc.Cleanup(options);

	//عدد الأنماط بعد تقليل التنظيف.
	Console.WriteLine(doc.Styles.Count);

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.CleanupDuplicateStyle.docx");

```