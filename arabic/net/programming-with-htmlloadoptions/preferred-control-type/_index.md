---
title: نوع التحكم المفضل
linktitle: نوع التحكم المفضل
second_title: Aspose.Words لمراجع .NET API
description: دليل تفصيلي خطوة بخطوة لتحديد نوع عنصر التحكم المفضل عند تحميل مستند HTML باستخدام Aspose.Words for .NET.
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

 نحن نستخدم ال`Document` فئة لتحميل كود HTML من تدفق الذاكرة مع خيارات التحميل المحددة مسبقًا. ثم نقوم بحفظ المستند في الدليل المحدد بامتداد`.docx` تنسيق الملف.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### مثال على شفرة المصدر لنوع التحكم المفضل مع Aspose.Words for .NET

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