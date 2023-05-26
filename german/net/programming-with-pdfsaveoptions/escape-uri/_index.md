---
title: الهروب أوري
linktitle: الهروب أوري
second_title: Aspose.Words لمراجع .NET API
description: دليل خطوة بخطوة للهروب من Uri باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /de/net/programming-with-pdfsaveoptions/escape-uri/
---

تقدم هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة Uri escape مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية إدراج الارتباطات التشعبية باستخدام Uri الهارب في مستند.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بإنشاء مستند و DocumentBuilder

 بعد ذلك ، نحتاج إلى إنشاء ملف`Document` كائن و`DocumentBuilder` كائن لبناء الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: أدخل الارتباطات التشعبية باستخدام مهرب Uri

 استخدم ال`InsertHyperlink` طريقة`DocumentBuilder`كائن لإدراج ارتباطات تشعبية في المستند. يجب أن يتم الهروب من Uri باستخدام امتداد`Uri.EscapeUriString` وظيفة لتجنب أخطاء التنسيق.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search؟q=٪2Fthe٪20test ") ، false) ؛
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search؟q=٪2Fthe٪20test ") ،
     Uri.EscapeUriString("https://www.google.com/search؟q=٪2Fthe٪20test ") ، false) ؛
```

## الخطوة 4: احفظ المستند كملف PDF

 أخيرًا ، يمكننا حفظ المستند كملف PDF باستخدام امتداد`Save` طريقة`Document` هدف. حدد اسم ملف الإخراج.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

هذا كل شئ ! لقد نجحت في إدراج الارتباطات التشعبية مع Uri's المهرب في مستند باستخدام Aspose.Words for .NET.

### عينة من التعليمات البرمجية المصدر لـ Uri escaping مع Aspose.Words for .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search؟q=٪2Fthe٪20test "، false)؛
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search؟q=٪2Fthe٪20test "،
		"https://www.google.com/search؟q=٪2Fthe٪20test "، false)؛

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```
