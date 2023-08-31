---
title: الهروب من URI في وثيقة PDF
linktitle: الهروب من URI في وثيقة PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة حول كيفية الهروب من URI في مستند PDF باستخدام Aspose.Words لـ .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/escape-uri/
---

توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية الهروب من URI في مستند PDF باستخدام Aspose.Words لـ .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستتمكن من فهم كيفية إدراج الارتباطات التشعبية باستخدام Uri الذي تم تجاوزه في المستند.

قبل البدء، تأكد من تثبيت وتكوين مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وتعليمات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء، تحتاج إلى تحديد المسار إلى الدليل الذي توجد به مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: إنشاء مستند وDocumentBuilder

 بعد ذلك، نحن بحاجة إلى إنشاء جديد`Document` كائن و`DocumentBuilder` كائن لبناء الوثيقة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## الخطوة 3: قم بإدراج الارتباطات التشعبية باستخدام Uri الهارب

 استخدم ال`InsertHyperlink` طريقة`DocumentBuilder` كائن لإدراج الارتباطات التشعبية في المستند. يجب الهروب من Uri باستخدام`Uri.EscapeUriString` وظيفة لتجنب أخطاء التنسيق.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"))،
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), false);
```

## الخطوة 4: احفظ المستند كملف PDF

 وأخيرًا، يمكننا حفظ المستند بصيغة PDF باستخدام ملف`Save` طريقة`Document` هدف. حدد اسم ملف الإخراج.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

هذا كل شئ ! لقد نجحت في إدراج الارتباطات التشعبية التي تحتوي على Uri الهارب في مستند باستخدام Aspose.Words for .NET.

### نموذج التعليمات البرمجية المصدر لهروب Uri باستخدام Aspose.Words لـ .NET


```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test"، false)؛
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test"،
		"https://www.google.com/search?q=%2Fthe%20test"، false)؛

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا كيفية الهروب من عناوين URI في مستند PDF باستخدام Aspose.Words for .NET. من خلال الهروب من عناوين URI، يمكنك تجنب أخطاء التنسيق والتأكد من تفسير الارتباطات التشعبية وعرضها بشكل صحيح في مستند PDF. اتبع الخطوات الموضحة لإدراج الارتباطات التشعبية ذات عناوين URI التي تم تجاوزها في مستند PDF الخاص بك. تأكد من الهروب.

### أسئلة مكررة

#### س: ما هو URI الخاص بالهروب في مستند PDF وما سبب أهميته؟
ج: يشير Escape URI في مستند PDF إلى طريقة تحويل الأحرف الخاصة في عنوان URL إلى تسلسلات هروب لتجنب أخطاء التنسيق. وهذا أمر مهم لأن الأحرف الخاصة في عنوان URL يمكن أن تعطل بنية عنوان URL وتؤدي إلى سوء التفسير أو العرض غير الصحيح. من خلال التخلص من الأحرف الخاصة، نضمن تفسير عنوان URL بشكل صحيح وعرضه في مستند PDF.

#### س: كيف يمكنني استخدام Aspose.Words لـ .NET للهروب من معرفات URI في مستند PDF؟
ج: للهروب من معرفات URI في مستند PDF باستخدام Aspose.Words لـ .NET، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد مستنداتك عن طريق الاستبدال`"YOUR DOCUMENT DIRECTORY"` بالمسار الفعلي لدليل المستندات الخاص بك.

 إنشاء مثيل جديد لـ`Document` فئة و أ`DocumentBuilder` كائن لبناء الوثيقة.

 استخدم ال`InsertHyperlink` طريقة`DocumentBuilder` كائن لإدراج الارتباطات التشعبية في المستند. تأكد من الهروب من URI باستخدام`Uri.EscapeUriString` وظيفة لتجنب أخطاء التنسيق.

 استخدم ال`Save` طريقة`Document` كائن لحفظ المستند بتنسيق PDF عن طريق تحديد اسم ملف الإخراج.

#### س: ما هي فوائد الهروب من عناوين URI في مستند PDF؟
ج: فوائد هروب URI في مستند PDF هي:

منع أخطاء التنسيق: يساعد هروب URI على منع أخطاء التنسيق الناتجة عن الأحرف الخاصة في عنوان URL، مما يضمن تفسير عنوان URL وعرضه بشكل صحيح في مستند PDF.

التوافق مع برامج قراءة PDF: يتم دعم معرفات URI التي تم تجاوزها بشكل جيد بشكل عام بواسطة برامج قراءة PDF، مما يضمن توافقًا أفضل وتجربة مستخدم متسقة.

#### س: ما هي الأحرف الخاصة التي يجب تجاوزها في URI؟
 ج: الأحرف الخاصة التي يجب تجاوزها في URI هي: space، <، >، "، #، %، {، }،|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.