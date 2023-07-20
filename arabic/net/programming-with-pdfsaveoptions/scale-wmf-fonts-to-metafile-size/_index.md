---
title: تقليل حجم PDF باستخدام Scale Wmf Fonts إلى Metafile Size
linktitle: تقليل حجم PDF باستخدام Scale Wmf Fonts إلى Metafile Size
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: دليل تفصيلي خطوة بخطوة لتقليل حجم pdf باستخدام مقياس خطوط wmf إلى حجم ملف التعريف عند التحويل إلى PDF باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

توفر هذه المقالة دليلًا تفصيليًا حول كيفية تقليل حجم pdf باستخدام مقياس خطوط wmf لميزة حجم ملف التعريف باستخدام Aspose.Words for .NET. سنشرح كل جزء من الكود بالتفصيل. في نهاية هذا البرنامج التعليمي ، ستتمكن من فهم كيفية تمكين أو تعطيل قياس خط WMF عند التحويل إلى PDF.

قبل أن تبدأ ، تأكد من تثبيت وتهيئة مكتبة Aspose.Words for .NET في مشروعك. يمكنك العثور على المكتبة وإرشادات التثبيت على موقع Aspose.

## الخطوة 1: تحديد دليل المستند

 للبدء ، تحتاج إلى تحديد المسار إلى الدليل حيث توجد مستنداتك. يستبدل`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي إلى دليل المستندات الخاص بك.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## الخطوة 2: قم بتحميل المستند

بعد ذلك ، نحتاج إلى تحميل المستند الذي نريد معالجته. في هذا المثال ، نفترض أن المستند يسمى "WMF with text.docx" ويقع في دليل المستندات المحدد.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## الخطوة 3: تكوين خيارات عرض ملف التعريف

 لتمكين أو تعطيل تحجيم خط WMF إلى حجم ملف التعريف ، نحتاج إلى تكوين ملف`MetafileRenderingOptions`هدف. في هذا المثال ، نقوم بتعطيل تحجيم الخط عن طريق تعيين الامتداد`ScaleWmfFontsToMetafileSize` الملكية ل`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## الخطوة 4: تكوين خيارات حفظ كملف PDF مع خيارات عرض ملف التعريف

أخيرًا ، يمكننا تكوين خيارات الحفظ إلى PDF باستخدام خيارات عرض ملف التعريف التي تم تكوينها مسبقًا.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## الخطوة 5: احفظ المستند بصيغة PDF باستخدام خيارات عرض ملف التعريف

احفظ المستند بتنسيق PDF باستخدام خيارات الحفظ التي تم تكوينها مسبقًا.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

هذا كل شئ ! لقد نجحت في تمكين أو تعطيل تحجيم خط WMF إلى حجم ملف التعريف عند التحويل

مستند PDF باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لمقياس خطوط WMF إلى حجم ملف التعريف باستخدام Aspose.Words for .NET

```csharp

	// المسار إلى دليل المستندات.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// إذا تعذر على Aspose.Words عرض بعض سجلات ملف التعريف بشكل صحيح إلى رسومات متجهة
	// ثم يعرض Aspose.Words ملف التعريف هذا إلى صورة نقطية.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## خاتمة

في هذا البرنامج التعليمي ، أوضحنا كيفية تمكين أو تعطيل تغيير حجم خطوط WMF إلى حجم ملف التعريف في مستند PDF باستخدام Aspose.Words for .NET. باتباع الخطوات الموضحة ، يمكنك التحكم بسهولة في ما إذا كان يجب تغيير حجم خطوط WMF لمطابقة حجم ملف التعريف عند التحويل إلى مستند PDF. يمكن أن يساعدك ذلك في تقليل حجم ملف PDF الذي تم إنشاؤه وتحسين أداء العرض. تأكد من تحديد المسار الصحيح للمستندات وتكوين خيارات عرض ملف التعريف حسب الحاجة.

### أسئلة مكررة

#### س: ما المقصود بتغيير حجم خطوط WMF إلى حجم ملف التعريف في مستند PDF؟
ج: يعد تغيير حجم خطوط WMF إلى حجم ملف التعريف في مستند PDF ميزة تتحكم في ما إذا كان يجب تغيير حجم خطوط WMF لمطابقة حجم ملف التعريف عند التحويل إلى مستند PDF. عند تمكين هذه الميزة ، يتم تحجيم خطوط WMF لمطابقة حجم ملف التعريف ، مما قد يقلل من حجم مستند PDF الذي تم إنشاؤه.

#### س: كيف يمكنني استخدام Aspose.Words for .NET لتمكين أو تعطيل تغيير حجم خطوط WMF إلى حجم ملف تعريف في مستند PDF؟
ج: لتمكين أو تعطيل تغيير حجم خطوط WMF إلى حجم ملف التعريف في مستند PDF باستخدام Aspose.Words for .NET ، اتبع الخطوات التالية:

 قم بتعيين مسار الدليل حيث توجد المستندات الخاصة بك عن طريق الاستبدال`"YOUR DOCUMENT DIRECTORY"` مع المسار الفعلي لدليل المستندات الخاص بك.

 قم بتحميل المستند الذي تريد معالجته باستخدام ملف`Document` class وحدد المسار إلى مستند Word في دليل المستندات المحدد.

 قم بتكوين خيارات عرض ملف التعريف عن طريق إنشاء مثيل لملف`MetafileRenderingOptions` الطبقة ووضع`ScaleWmfFontsToMetafileSize` الملكية ل`true` لتمكين تحجيم خطوط WMF إلى حجم ملف التعريف ، أو إلى`false` لتعطيل هذه الميزة.

 قم بتكوين خيارات الحفظ بتنسيق PDF بإنشاء مثيل لملف`PdfSaveOptions` فئة واستخدام خيارات عرض ملف التعريف التي تم تكوينها مسبقًا.

 احفظ المستند بتنسيق PDF باستخدام ملف`Save` طريقة`Document`فئة تحدد المسار وخيارات الحفظ.

#### س: ما هي فوائد تغيير حجم خطوط WMF إلى حجم ملف التعريف في مستند PDF؟
ج: مزايا تغيير حجم خطوط WMF إلى حجم ملف تعريف في مستند PDF هي:

تقليل حجم ملف PDF: يمكن أن يؤدي تغيير حجم خطوط WMF إلى حجم ملف التعريف إلى تقليل حجم مستند PDF الذي تم إنشاؤه عن طريق تكييف حجم الخط مع احتياجات ملف التعريف.

أداء محسّن: من خلال ضبط حجم خطوط WMF على أبعاد ملف التعريف ، يمكن أن يكون عرض مستند PDF أسرع وأكثر كفاءة.