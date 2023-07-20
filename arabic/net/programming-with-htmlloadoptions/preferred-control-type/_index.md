---
title: نوع التحكم المفضل في مستند Word
linktitle: نوع التحكم المفضل في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل تفصيلي خطوة بخطوة لتحديد نوع عنصر التحكم المفضل في مستند Word عند تحميل مستند HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlloadoptions/preferred-control-type/
---
توفر هذه المقالة دليلًا تفصيليًا حول كيفية استخدام ميزة نوع عنصر التحكم المفضل مع Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تحديد نوع عنصر التحكم المفضل عند تحميل مستند HTML.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد كود HTML

 للبدء ، تحتاج إلى تحديد كود HTML الذي تريد تحميله كمستند. في هذا المثال ، قمنا بتعريف ملف`html` متغير يحتوي على كود HTML لمحدد مع خيارات.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## الخطوة 2: تعيين خيارات تحميل HTML

 بعد ذلك ، نقوم بإنشاء ملف`HtmlLoadOptions` كائن وتعيين`PreferredControlType` الملكية ل`HtmlControlType.StructuredDocumentTag`. هذا يخبر Aspose.Words باستخدام StructuredDocumentTags لتمثيل HTML عند التحميل.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## الخطوة 3: تحميل وحفظ المستند

 نحن نستخدم ال`Document` فئة لتحميل كود HTML من تدفق الذاكرة مع خيارات التحميل المحددة مسبقًا. ثم نقوم بحفظ المستند في الدليل المحدد بامتداد`.docx`تنسيق الملف.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### مثال على كود المصدر لنوع التحكم المفضل مع Aspose.Words for .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

هذا كل شئ ! لقد نجحت في تحديد نوع عنصر التحكم المفضل عند تحميل مستند HTML باستخدام Aspose.Words for .NET.

## خاتمة

 باتباع هذا الدليل المفصل خطوة بخطوة ، تعلمت كيفية استخدام ميزة "نوع التحكم المفضل" في Aspose.Words for .NET لتحديد نوع عنصر التحكم المطلوب عند تحميل مستند HTML. وضع`PreferredControlType` الملكية ل`HtmlControlType.StructuredDocumentTag` يسمح لـ Aspose.Words باستخدام StructuredDocumentTags (SDT) لتمثيل محتوى HTML ومعالجته بشكل أفضل. يمكنك استكشاف أنواع التحكم الأخرى أيضًا لتناسب متطلباتك الخاصة. يساعد استخدام هذه الميزة في ضمان معالجة دقيقة وفعالة لمستندات HTML في تطبيق C # باستخدام Aspose.Words.

### الأسئلة الشائعة حول نوع التحكم المفضل في مستند Word

#### س: ما هي ميزة "نوع التحكم المفضل" في Aspose.Words for .NET؟

ج: تسمح لك ميزة "نوع التحكم المفضل" بتحديد نوع التحكم المفضل لتمثيل عناصر HTML عند تحميل مستند HTML. يساعد في اختيار نوع التحكم المناسب لتحسين تمثيل ومعالجة محتوى HTML.

#### س: كيف يمكنني تعيين نوع عنصر التحكم المفضل عند تحميل مستند HTML؟

 ج: لتعيين نوع عنصر التحكم المفضل ، يلزمك إنشاء ملف`HtmlLoadOptions` الكائن وتعيينه`PreferredControlType` الممتلكات إلى المطلوب`HtmlControlType` . في المثال المقدم ،`HtmlControlType.StructuredDocumentTag` يستخدم.

#### س: ما أهمية استخدام StructuredDocumentTags (SDT) كنوع التحكم المفضل؟

ج: StructuredDocumentTags (SDT) هي عناصر قائمة على XML يمكن استخدامها لتمثيل المحتوى المعقد وعناصر التحكم في مستند Word. يمكن أن يوفر استخدام SDTs كنوع التحكم المفضل توافقًا وتمثيلًا أفضل لمحتوى HTML.

#### س: كيف يمكنني التأكد من أن Aspose.Words يستخدم نوع التحكم المفضل عند تحميل مستند HTML؟

 ج: من خلال ضبط ملف`PreferredControlType` الملكية ل`HtmlControlType.StructuredDocumentTag`، كما هو موضح في مثال الكود المصدري ، سوف تستخدم Aspose.Words أدوات القياس والمعايير لتمثيل عناصر HTML عند تحميل المستند.

#### س: هل يمكنني استخدام أنواع تحكم أخرى كخيار مفضل؟

 ج: نعم ، بصرف النظر عن`HtmlControlType.StructuredDocumentTag` يدعم Aspose.Words for .NET أنواع التحكم الأخرى مثل`HtmlControlType.ContentControl` و`HtmlControlType.CustomXmlMarkup`.