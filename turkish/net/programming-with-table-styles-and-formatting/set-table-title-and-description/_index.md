---
title: تعيين عنوان الجدول ووصفه
linktitle: تعيين عنوان الجدول ووصفه
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لتعيين عنوان ووصف للجدول باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /tr/net/programming-with-table-styles-and-formatting/set-table-title-and-description/
---

في هذا البرنامج التعليمي ، سنرشدك خلال العملية خطوة بخطوة لتعيين عنوان الجدول ووصفه باستخدام Aspose.Words for .NET. سنشرح الكود المصدري C # المجمّع ونزودك بدليل شامل لمساعدتك على فهم هذه الميزة وتنفيذها في مشاريعك الخاصة. في نهاية هذا البرنامج التعليمي ، ستعرف كيفية إضافة عنوان ووصف إلى جدول في مستندات Word باستخدام Aspose.Words for .NET.

## الخطوة 1: تحديد دليل المستند
أولاً ، تحتاج إلى تعيين المسار إلى دليل المستندات الخاص بك. هذا هو المكان الذي تريد حفظ مستند Word الذي تم تحريره فيه. استبدل "دليل المستندات" بالمسار المناسب.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند الذي يحتوي على الجدول
 بعد ذلك ، تحتاج إلى تحميل المستند الذي يحتوي على الجدول باستخدام ملف`Document` فصل. تأكد من تحديد مسار المستند الصحيح.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## الخطوة 3: قم بالوصول إلى الجدول وقم بتعيين العنوان والوصف
 يمكنك الآن الوصول إلى الجدول الموجود في المستند باستخدام ملف`GetChild()` الطريقة و`Table` فصل. بعد ذلك ، قم بتعيين عنوان الجدول ووصفه باستخدام ملف`Title` و`Description` ملكيات.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table.Title = "Test Title";
table.Description = "Test Description";
```

## الخطوة 4: تعيين خيارات النسخ الاحتياطي
 إذا كنت تريد تحديد خيارات الحفظ ، فيمكنك تهيئتها باستخدام ملف`OoxmlSaveOptions` فصل. في هذا المثال ، استخدمنا الامتداد`Compliance` الخيار لتحديد التوافق مع تنسيق ISO 29500: 2008 الصارم.

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };
```

## الخطوة 5: تحسين توافق المستندات
 يمكنك أيضًا تحسين توافق المستندات باستخدام تنسيق`OptimizeFor()` طريقة`CompatibilityOptions` فصل. في هذا المثال ، قمنا بتحسين المستند لـ Word 2016.

```csharp
doc.CompatibilityOptions.OptimizeFor(Aspose.Words.Settings.MsWordVersion.Word2016);
```

## الخطوة 6: احفظ المستند المعدل
 أخيرًا ، يمكنك حفظ المستند المعدل في ملف باستخدام امتداد`Save()` طريقة`Document` فصل. تأكد من تحديد المسار الصحيح واسم الملف.



```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetTableTitleAndDescription.docx", options);
```

### عينة من التعليمات البرمجية المصدر لـ Set Table Title and Description باستخدام Aspose.Words for .NET 

```csharp
	// المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.Title = "Test title";
	table.Description = "Test description";
	OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Strict };
	doc.CompatibilityOptions.OptimizeFor(Aspose.Words.Settings.MsWordVersion.Word2016);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetTableTitleAndDescription.docx", options);
```

## خاتمة
في هذا البرنامج التعليمي ، تعلمنا كيفية تعيين عنوان الجدول ووصفه باستخدام Aspose.Words for .NET. باتباع هذا الدليل التفصيلي خطوة بخطوة ، يمكنك بسهولة إضافة عنوان ووصف إلى جدول في مستندات Word الخاصة بك. يقدم Aspose.Words واجهة برمجة تطبيقات قوية ومرنة لمعالجة الجداول وتنسيقها في مستنداتك. باستخدام هذه المعرفة ، يمكنك تخصيص البنية والمعلومات المرتبطة بجداولك وفقًا لاحتياجاتك الخاصة.