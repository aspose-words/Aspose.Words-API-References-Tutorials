---
title: ضغط الصور في وثيقة PDF
linktitle: ضغط الصور في وثيقة PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة المستندات
description: تعرف على كيفية ضغط الصور في مستندات PDF باستخدام Aspose.Words for .NET. اتبع هذا الدليل لتحسين حجم الملف وجودته.
type: docs
weight: 10
url: /ar/net/programming-with-pdfsaveoptions/image-compression/
---
## مقدمة

في العصر الرقمي الحالي، تعد إدارة حجم المستند أمرًا بالغ الأهمية لكل من الأداء وكفاءة التخزين. سواء كنت تتعامل مع تقارير كبيرة أو عروض تقديمية معقدة، فإن تقليل حجم الملف دون التضحية بالجودة يعد أمرًا ضروريًا. يعد ضغط الصور في مستندات PDF تقنية أساسية لتحقيق هذا الهدف. إذا كنت تعمل مع Aspose.Words لـ .NET، فأنت محظوظ! سيرشدك هذا البرنامج التعليمي خلال عملية ضغط الصور في مستندات PDF باستخدام Aspose.Words for .NET. سنستكشف خيارات الضغط المختلفة وكيفية تطبيقها بفعالية لضمان تحسين ملفات PDF الخاصة بك من حيث الجودة والحجم.

## المتطلبات الأساسية

قبل الغوص في البرنامج التعليمي، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Words لـ .NET: أنت بحاجة إلى تثبيت Aspose.Words لـ .NET. يمكنك تنزيله من[موقع أسبوز](https://releases.aspose.com/words/net/).

2. المعرفة الأساسية بـ C#: الإلمام ببرمجة C# سيساعدك على فهم أمثلة التعليمات البرمجية المتوفرة في هذا البرنامج التعليمي.

3. بيئة التطوير: تأكد من إعداد بيئة تطوير .NET، مثل Visual Studio.

4. نموذج مستند: احصل على نموذج مستند Word (على سبيل المثال، "Rendering.docx") جاهز لاختبار ضغط الصور.

5. ترخيص Aspose: إذا كنت تستخدم إصدارًا مرخصًا من Aspose.Words لـ .NET، فتأكد من تكوين الترخيص بشكل صحيح. إذا كنت بحاجة إلى ترخيص مؤقت، يمكنك الحصول عليه من[صفحة الترخيص المؤقت لـ Aspose](https://purchase.aspose.com/temporary-license/).

## استيراد مساحات الأسماء

للبدء في ضغط الصور في مستندات PDF باستخدام Aspose.Words لـ .NET، تحتاج إلى استيراد مساحات الأسماء الضرورية. إليك كيفية القيام بذلك:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

توفر مساحات الأسماء هذه إمكانية الوصول إلى الوظائف الأساسية اللازمة لمعالجة مستندات Word وحفظها كملفات PDF مع خيارات متنوعة.

## الخطوة 1: قم بإعداد دليل المستندات الخاص بك

قبل البدء في البرمجة، حدد المسار إلى دليل المستندات الخاص بك. سيساعدك هذا على تحديد موقع ملفاتك وحفظها بسهولة.

```csharp
// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 يستبدل`"YOUR DOCUMENT DIRECTORY"` بالمسار حيث تم تخزين مستند العينة الخاص بك.

## الخطوة 2: قم بتحميل مستند Word

 بعد ذلك، قم بتحميل مستند Word الخاص بك إلى ملف`Aspose.Words.Document` هدف. سيسمح لك هذا بالعمل مع المستند برمجياً.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 هنا،`"Rendering.docx"` هو اسم مستند Word النموذجي. تأكد من وجود هذا الملف في الدليل المحدد.

## الخطوة 3: تكوين ضغط الصور الأساسي

 إنشاء أ`PdfSaveOptions`الكائن لتكوين خيارات حفظ PDF، بما في ذلك ضغط الصور. تعيين`ImageCompression`الملكية ل`PdfImageCompression.Jpeg` لاستخدام ضغط JPEG للصور.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	// ضغط الصور باستخدام JPEG
    ImageCompression = PdfImageCompression.Jpeg,
	// اختياري: احتفظ بحقول النموذج في ملف PDF
    PreserveFormFields = true
};
```

## الخطوة 4: احفظ المستند بالضغط الأساسي

احفظ مستند Word كملف PDF باستخدام خيارات ضغط الصور التي تم تكوينها. سيؤدي هذا إلى تطبيق ضغط JPEG على الصور الموجودة في ملف PDF.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

 في هذا المثال، تمت تسمية ملف PDF الناتج`"WorkingWithPdfSaveOptions.PdfImageCompression.pdf"`. اضبط اسم الملف حسب الحاجة.

## الخطوة 5: تكوين الضغط المتقدم مع التوافق مع PDF/A

 للحصول على ضغط أفضل، خاصة إذا كنت بحاجة إلى الالتزام بمعايير PDF/A، يمكنك تكوين خيارات إضافية. تعيين`Compliance`الملكية ل`PdfCompliance.PdfA2u` وضبط`JpegQuality` ملكية.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
	// اضبط التوافق على PDF/A-2u
    Compliance = PdfCompliance.PdfA2u,
	// استخدم ضغط JPEG
    ImageCompression = PdfImageCompression.Jpeg,
	// اضبط جودة JPEG للتحكم في مستوى الضغط
    JpegQuality = 100 
};
```

## الخطوة 6: احفظ المستند بالضغط المتقدم

احفظ مستند Word كملف PDF باستخدام إعدادات الضغط المتقدمة. يضمن هذا التكوين أن يلتزم ملف PDF بمعايير PDF/A ويستخدم ضغط JPEG عالي الجودة.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```

 هنا، تتم تسمية ملف PDF الناتج`"WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf"`. قم بتعديل اسم الملف وفقًا لتفضيلاتك.

## خاتمة

يعد تقليل حجم مستندات PDF عن طريق ضغط الصور خطوة حيوية في تحسين أداء المستند وتخزينه. باستخدام Aspose.Words for .NET، لديك أدوات قوية تحت تصرفك للتحكم في ضغط الصور بشكل فعال. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك التأكد من أن مستندات PDF الخاصة بك عالية الجودة وصغيرة الحجم. سواء كنت بحاجة إلى ضغط أساسي أو متقدم، فإن Aspose.Words يوفر المرونة اللازمة لتلبية احتياجاتك.


## الأسئلة الشائعة

### ما هو ضغط الصور في ملفات PDF؟
يؤدي ضغط الصور إلى تقليل حجم ملف مستندات PDF عن طريق تقليل جودة الصور، مما يساعد في تحسين التخزين والأداء.

### كيف يتعامل Aspose.Words لـ .NET مع ضغط الصور؟
يوفر Aspose.Words لـ .NET`PdfSaveOptions` فئة، والتي تسمح لك بتعيين خيارات ضغط الصور المختلفة، بما في ذلك ضغط JPEG.

### هل يمكنني استخدام Aspose.Words لـ .NET للتوافق مع معايير PDF/A؟
نعم، يدعم Aspose.Words التوافق مع PDF/A، مما يسمح لك بحفظ المستندات بتنسيقات تلبي معايير الأرشفة والحفظ طويل المدى.

### ما هو تأثير جودة JPEG على حجم ملف PDF؟
تؤدي إعدادات جودة JPEG الأعلى إلى جودة صورة أفضل ولكن أحجام ملفات أكبر، بينما تؤدي إعدادات الجودة المنخفضة إلى تقليل حجم الملف ولكنها قد تؤثر على وضوح الصورة.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Words لـ .NET؟
 يمكنك استكشاف المزيد حول Aspose.Words for .NET على موقعهم[التوثيق](https://reference.aspose.com/words/net/), [يدعم](https://forum.aspose.com/c/words/8) ، و[تحميل](https://releases.aspose.com/words/net/) الصفحات.

### نموذج التعليمات البرمجية المصدر لضغط الصور باستخدام Aspose.Words لـ .NET

```csharp

// المسار إلى دليل المستندات.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");

PdfSaveOptions saveOptions = new PdfSaveOptions
{
	ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
};

doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
	Compliance = PdfCompliance.PdfA2u,
	ImageCompression = PdfImageCompression.Jpeg,
	JpegQuality = 100, // استخدم ضغط JPEG بجودة 50% لتقليل حجم الملف.
};



doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```