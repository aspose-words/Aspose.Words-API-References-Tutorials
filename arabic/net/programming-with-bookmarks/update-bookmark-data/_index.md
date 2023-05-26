---
title: تحديث البيانات المرجعية
linktitle: تحديث البيانات المرجعية
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة لشرح شفرة المصدر C # لميزة تحديث بيانات الإشارة المرجعية Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-bookmarks/update-bookmark-data/
---

في هذا البرنامج التعليمي ، سننتقل عبر دليل تفصيلي خطوة بخطوة لفهم ميزة تحديث بيانات الإشارة المرجعية وتنفيذها في Aspose.Words for .NET. تتيح لك هذه الميزة تحديث محتوى وخصائص الإشارات المرجعية داخل مستند Word باستخدام كود مصدر C #.

## متطلبات

قبل متابعة البرنامج التعليمي ، تأكد من توفر المتطلبات التالية:

- تثبيت Aspose.Words لمكتبة .NET
- المعرفة الأساسية بلغة البرمجة C #
- Visual Studio أو أي IDE متوافق آخر

## الخطوة 1: قم بتحميل المستند

في هذه الخطوة ، سنقوم بتحميل مستند Word الذي يحتوي على الإشارات المرجعية التي نريد تحديثها. بافتراض أن لديك المستند مخزّنًا في دليل معين ، استخدم الكود التالي لتحميل المستند:

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع مسار الدليل الفعلي حيث يوجد المستند الخاص بك.

## الخطوة 2: الوصول إلى الإشارة المرجعية

لتحديث بيانات الإشارة المرجعية ، نحتاج أولاً إلى الوصول إلى الإشارة المرجعية المحددة داخل المستند. كل إشارة مرجعية لها اسم فريد مرتبط بها. استخدم الكود التالي للوصول إلى إشارة مرجعية تسمى "MyBookmark1":

```csharp
Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];
```

تأكد من تطابق اسم الإشارة المرجعية مع الاسم الموجود في المستند. يمكنك تعديله حسب متطلباتك.

## الخطوة 3: تحديث خصائص الإشارات المرجعية والمحتوى

بمجرد الوصول إلى الإشارة المرجعية ، يمكنك تحديث خصائصها ومحتواها. في مقتطف الشفرة التالي ، سنقوم بتحديث اسم الإشارة المرجعية ونصها:

```csharp
string name = bookmark.Name;
string text = bookmark.Text;

bookmark.Name = "RenamedBookmark";
bookmark.Text = "This is a new bookmarked text.";
```

يمكنك تخصيص اسم الإشارة المرجعية والنص الجديد وفقًا لاحتياجاتك. الرمز أعلاه يعيد تسمية الإشارة المرجعية إلى "RenamedBookmark" ويقوم بتحديث محتوى النص.

## الخطوة 4: احفظ المستند المحدث

بعد تحديث بيانات الإشارة المرجعية ، تحتاج إلى حفظ المستند المعدل. استخدم الكود التالي لحفظ المستند:

```csharp
doc.Save(dataDir + "UpdatedDocument.docx");
```

سيحفظ هذا الرمز المستند المعدل باسم "UpdatedDocument.docx" في نفس الدليل مثل المستند الأصلي.

### مثال على شفرة المصدر لتحديث بيانات الإشارة المرجعية باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	Bookmark bookmark = doc.Range.Bookmarks["MyBookmark1"];

	string name = bookmark.Name;
	string text = bookmark.Text;

	bookmark.Name = "RenamedBookmark";
	bookmark.Text = "This is a new bookmarked text.";

```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` مع مسار الدليل الفعلي حيث يوجد المستند الخاص بك.

## خاتمة

تهانينا! لقد تعلمت بنجاح كيفية تحديث بيانات الإشارات المرجعية باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة المقدم في هذا البرنامج التعليمي ، يجب أن تكون قادرًا الآن على دمج هذه الميزة في تطبيقات C # الخاصة بك ومعالجة الإشارات المرجعية في مستندات Word برمجيًا.