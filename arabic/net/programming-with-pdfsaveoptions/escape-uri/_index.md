---
title: Escape URI في مستند PDF
linktitle: Escape URI في مستند PDF
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة كيفية الهروب من URI في مستند PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/escape-uri/
---

تقدم هذه المقالة دليلاً خطوة بخطوة حول كيفية Escape URI في مستند PDF باستخدام Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية إدراج الارتباطات التشعبية باستخدام Uri الهارب في مستند.

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

 استخدم ال`InsertHyperlink` طريقة`DocumentBuilder` كائن لإدراج ارتباطات تشعبية في المستند. يجب أن يتم الهروب من Uri باستخدام امتداد`Uri.EscapeUriString` وظيفة لتجنب أخطاء التنسيق.

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

## خاتمة

في هذا البرنامج التعليمي ، تناولنا كيفية التخلص من URIs في مستند PDF باستخدام Aspose.Words for .NET. من خلال الهروب من URIs ، يمكنك تجنب أخطاء التنسيق والتأكد من تفسير الروابط التشعبية وعرضها بشكل صحيح في مستند PDF. اتبع الخطوات الموضحة لإدراج الارتباطات التشعبية مع URIs التي تم تجاوزها في مستند PDF الخاص بك. تأكد من الهروب.

### أسئلة مكررة

#### س: ما هو الهروب URI في مستند PDF ولماذا هو مهم؟
ج: يشير Escape URI في مستند PDF إلى طريقة تحويل الأحرف الخاصة في عنوان URL إلى تسلسلات هروب لتجنب أخطاء التنسيق. هذا مهم لأن الأحرف الخاصة في عنوان URL يمكن أن تعطل بنية عنوان URL وتؤدي إلى التفسير الخاطئ أو العرض غير الصحيح. من خلال تخطي الأحرف الخاصة ، نضمن أن عنوان URL يتم تفسيره وعرضه بشكل صحيح في مستند PDF.

#### س: كيف يمكنني استخدام Aspose.Words for .NET لإلغاء URIs في مستند PDF؟
ج: للتخلص من URIs في مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد المستندات الخاصة بك عن طريق الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لدليل المستندات الخاص بك.

 قم بإنشاء مثيل جديد لملف`Document` فئة وأ`DocumentBuilder` كائن لبناء الوثيقة.

 استخدم ال`InsertHyperlink` طريقة`DocumentBuilder` كائن لإدراج ارتباطات تشعبية في المستند. تأكد من الهروب من URI باستخدام امتداد`Uri.EscapeUriString` وظيفة لتجنب أخطاء التنسيق.

 استخدم ال`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF عن طريق تحديد اسم الملف الناتج.

#### س: ما هي فوائد الهروب من URIs في مستند PDF؟
ج: فوائد هروب URI في مستند PDF هي:

منع أخطاء التنسيق: يساعد هروب URI في منع أخطاء التنسيق التي تسببها الأحرف الخاصة في عنوان URL ، مما يضمن تفسير عنوان URL بشكل صحيح وعرضه في مستند PDF.

التوافق مع برامج قراءة ملفات PDF: يتم دعم URIs بشكل عام بشكل جيد بواسطة برامج قراءة PDF ، مما يضمن توافقًا أفضل وتجربة مستخدم متسقة.

#### س: ما هي الأحرف الخاصة التي يجب تخطيها في URI؟
 ج: الأحرف الخاصة التي يجب تخطيها في URI هي: space، <،>، "، #،٪، {،}،|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.