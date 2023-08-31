---
title: نوع التحكم المفضل في مستند Word
linktitle: نوع التحكم المفضل في مستند Word
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: دليل خطوة بخطوة لتحديد نوع التحكم المفضل في مستند Word عند تحميل مستند HTML باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-htmlloadoptions/preferred-control-type/
---
توفر هذه المقالة دليلاً خطوة بخطوة حول كيفية استخدام ميزة نوع التحكم المفضل مع Aspose.Words لـ .NET. وسنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي، ستتمكن من فهم كيفية تحديد نوع التحكم المفضل عند تحميل مستند HTML.

قبل البدء، تأكد من تثبيت وتكوين مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وتعليمات التثبيت على موقع Aspose.

## الخطوة 1: تحديد كود HTML

 للبدء، تحتاج إلى تحديد كود HTML الذي تريد تحميله كمستند. في هذا المثال، قمنا بتحديد`html` متغير يحتوي على كود HTML الخاص بالمحدد مع الخيارات.

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

## الخطوة 2: قم بتعيين خيارات تحميل HTML

 بعد ذلك، نقوم بإنشاء`HtmlLoadOptions` الكائن وتعيين`PreferredControlType` الملكية ل`HtmlControlType.StructuredDocumentTag`. هذا يخبر Aspose.Words باستخدام StructuredDocumentTags لتمثيل HTML عند التحميل.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## الخطوة 3: تحميل وحفظ المستند

 نحن نستخدم ال`Document` فئة لتحميل كود HTML من تدفق الذاكرة مع خيارات التحميل المحددة مسبقًا. ثم نقوم بحفظ المستند في الدليل المحدد بالملحق`.docx`تنسيق الملف.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### مثال على التعليمات البرمجية المصدر لنوع التحكم المفضل باستخدام Aspose.Words لـ .NET

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

هذا كل شئ ! لقد نجحت في تحديد نوع التحكم المفضل عند تحميل مستند HTML باستخدام Aspose.Words لـ .NET.

## خاتمة

 باتباع هذا الدليل خطوة بخطوة، تكون قد تعلمت كيفية استخدام ميزة "نوع التحكم المفضل" في Aspose.Words لـ .NET لتحديد نوع التحكم المطلوب عند تحميل مستند HTML. وضع`PreferredControlType` الملكية ل`HtmlControlType.StructuredDocumentTag` يسمح لـ Aspose.Words باستخدام StructuredDocumentTags (SDT) لتمثيل محتوى HTML ومعالجته بشكل أفضل. يمكنك استكشاف أنواع التحكم الأخرى أيضًا لتناسب متطلباتك المحددة. يساعد استخدام هذه الميزة على ضمان معالجة دقيقة وفعالة لمستندات HTML في تطبيق C# الخاص بك باستخدام Aspose.Words.

### الأسئلة الشائعة حول نوع التحكم المفضل في مستند Word

#### س: ما هي ميزة "نوع التحكم المفضل" في Aspose.Words لـ .NET؟

ج: تتيح لك ميزة "نوع التحكم المفضل" تحديد نوع التحكم المفضل لتمثيل عناصر HTML عند تحميل مستند HTML. فهو يساعد في اختيار نوع التحكم المناسب لتمثيل ومعالجة محتوى HTML بشكل أفضل.

#### س: كيف أقوم بتعيين نوع التحكم المفضل عند تحميل مستند HTML؟

 ج: لتعيين نوع التحكم المفضل، تحتاج إلى إنشاء`HtmlLoadOptions` الكائن وتعيينه`PreferredControlType` الملكية إلى المطلوب`HtmlControlType` . في المثال المقدم،`HtmlControlType.StructuredDocumentTag` يستخدم.

#### س: ما أهمية استخدام StructuredDocumentTags (SDT) كنوع التحكم المفضل؟

ج: StructuredDocumentTags (SDT) عبارة عن عناصر مستندة إلى XML يمكن استخدامها لتمثيل المحتوى المعقد وعناصر التحكم في مستند Word. يمكن أن يؤدي استخدام SDTs كنوع التحكم المفضل إلى توفير توافق وتمثيل أفضل لمحتوى HTML.

#### س: كيف يمكنني التأكد من أن Aspose.Words يستخدم نوع التحكم المفضل عند تحميل مستند HTML؟

 ج: من خلال تحديد`PreferredControlType` الملكية ل`HtmlControlType.StructuredDocumentTag`كما هو موضح في مثال التعليمات البرمجية المصدر، سوف يستخدم Aspose.Words SDTs لتمثيل عناصر HTML عند تحميل المستند.

#### س: هل يمكنني استخدام أنواع التحكم الأخرى كخيار مفضل؟

 ج: نعم، فيما عدا ذلك`HtmlControlType.StructuredDocumentTag` يدعم Aspose.Words for .NET أنواع التحكم الأخرى مثل`HtmlControlType.ContentControl` و`HtmlControlType.CustomXmlMarkup`.