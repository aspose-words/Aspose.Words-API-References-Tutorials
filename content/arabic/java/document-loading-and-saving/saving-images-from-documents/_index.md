---
title: حفظ الصور من المستندات في Aspose.Words لـ Java
linktitle: حفظ الصور من المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية حفظ الصور من المستندات باستخدام Aspose.Words for Java من خلال دليلنا الشامل خطوة بخطوة. تخصيص التنسيقات والضغط والمزيد.
type: docs
weight: 17
url: /ar/java/document-loading-and-saving/saving-images-from-documents/
---

## مقدمة لحفظ الصور من المستندات في Aspose.Words لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية حفظ الصور من المستندات باستخدام Aspose.Words for Java. سنغطي السيناريوهات المختلفة وخيارات التخصيص لحفظ الصور. يوفر هذا الدليل إرشادات خطوة بخطوة مع أمثلة التعليمات البرمجية المصدر.

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من دمج مكتبة Aspose.Words for Java في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).

## الخطوة 1: حفظ الصور بتنسيق TIFF مع التحكم في العتبة

لحفظ الصور بتنسيق TIFF مع التحكم في العتبة، اتبع الخطوات التالية:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
doc.save("Your Directory Path" + "ThresholdControlledImage.tiff", saveOptions);
```

## الخطوة 2: حفظ صفحة معينة بتنسيق TIFF متعدد الصفحات

لحفظ صفحة معينة كملف TIFF متعدد الصفحات، استخدم الكود التالي:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
saveOptions.setPageSet(new PageSet(new PageRange(0, 1)));
saveOptions.setTiffCompression(TiffCompression.CCITT_4);
saveOptions.setResolution(160f);
doc.save("Your Directory Path" + "SpecificPageMultipage.tiff", saveOptions);
```

## الخطوة 3: حفظ الصور بتنسيق 1 BPP مفهرسة PNG

لحفظ الصور بتنسيق PNG مفهرس BPP واحد، اتبع الخطوات التالية:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(1));
saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
doc.save("Your Directory Path" + "1BPPIndexed.png", saveOptions);
```

## الخطوة 4: حفظ الصفحة بتنسيق JPEG مع التخصيص

لحفظ صفحة معينة بصيغة JPEG مع خيارات التخصيص، استخدم هذا الرمز:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
options.setPageSet(new PageSet(0));
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
options.setHorizontalResolution(72f);
doc.save("Your Directory Path" + "CustomizedJPEG.jpeg", options);
```

## الخطوة 5: استخدام رد الاتصال لحفظ الصفحة

يمكنك استخدام رد الاتصال لتخصيص حفظ الصفحة. هنا مثال:

```java
Document doc = new Document("Your Directory Path" + "Rendering.docx");
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
doc.save("Your Directory Path" + "PageSavingCallback.png", imageSaveOptions);
```

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```

## كود المصدر الكامل لحفظ الصور من المستندات في Aspose.Words لـ Java

```java
public void exposeThresholdControlForTiffBinarization() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setTiffCompression(TiffCompression.CCITT_3);
		saveOptions.setImageColorMode(ImageColorMode.GRAYSCALE);
		saveOptions.setTiffBinarizationMethod(ImageBinarizationMethod.FLOYD_STEINBERG_DITHERING);
		saveOptions.setThresholdForFloydSteinbergDithering((byte) 254);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.ExposeThresholdControlForTiffBinarization.tiff", saveOptions);
}
@Test
public void getTiffPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.TIFF);
	{
		saveOptions.setPageSet(new PageSet(new PageRange(0, 1))); saveOptions.setTiffCompression(TiffCompression.CCITT_4); saveOptions.setResolution(160f);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
}
@Test
public void format1BppIndexed() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		saveOptions.setPageSet(new PageSet(1));
		saveOptions.setImageColorMode(ImageColorMode.BLACK_AND_WHITE);
		saveOptions.setPixelFormat(ImagePixelFormat.FORMAT_1_BPP_INDEXED);
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
}
@Test
public void getJpegPageRange() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions options = new ImageSaveOptions(SaveFormat.JPEG);
	// اضبط "PageSet" على "0" لتحويل الصفحة الأولى فقط من المستند.
	options.setPageSet(new PageSet(0));
	// تغيير سطوع الصورة والتباين.
	// كلاهما على مقياس 0-1 ويكون عند 0.5 بشكل افتراضي.
	options.setImageBrightness(0.3f);
	options.setImageContrast(0.7f);
	// تغيير الدقة الأفقية.
	// القيمة الافتراضية لهذه الخصائص هي 96.0، لدقة تبلغ 96 نقطة في البوصة.
	options.setHorizontalResolution(72f);
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
}
@Test
public static void pageSavingCallback() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Rendering.docx");
	ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.PNG);
	{
		imageSaveOptions.setPageSet(new PageSet(new PageRange(0, doc.getPageCount() - 1)));
		imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
	}
	doc.save("Your Directory Path" + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
}
private static class HandlePageSavingCallback implements IPageSavingCallback
{
	public void pageSaving(PageSavingArgs args)
	{
		args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
	}
```

## خاتمة

لقد تعلمت كيفية حفظ الصور من المستندات باستخدام Aspose.Words for Java. توضح هذه الأمثلة خيارات التخصيص المتنوعة لحفظ الصورة، بما في ذلك التنسيق والضغط واستخدام رد الاتصال. اكتشف المزيد من الإمكانيات باستخدام Aspose.Words لإمكانيات Java القوية.

## الأسئلة الشائعة

### كيف يمكنني تغيير تنسيق الصورة عند الحفظ باستخدام Aspose.Words لـ Java؟

 يمكنك تغيير تنسيق الصورة عن طريق تحديد التنسيق المطلوب في ملف`ImageSaveOptions` . على سبيل المثال، للحفظ بتنسيق PNG، استخدم`SaveFormat.PNG` كما هو موضح في الكود:

```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
```

### هل يمكنني تخصيص إعدادات الضغط لصور TIFF؟

نعم، يمكنك تخصيص إعدادات ضغط الصور TIFF. على سبيل المثال، لتعيين طريقة الضغط على CCITT_3، استخدم الكود التالي:

```java
saveOptions.setTiffCompression(TiffCompression.CCITT_3);
```

### كيف يمكنني حفظ صفحة معينة من مستند كصورة منفصلة؟

 لحفظ صفحة معينة كصورة، استخدم`setPageSet`طريقة في`ImageSaveOptions` . على سبيل المثال، لحفظ الصفحة الأولى فقط، قم بتعيين`PageSet` ل`new PageSet(0)`.

```java
saveOptions.setPageSet(new PageSet(0)); // احفظ الصفحة الأولى كصورة
```

### كيف يمكنني تطبيق الإعدادات المخصصة على صور JPEG عند الحفظ؟

يمكنك تطبيق الإعدادات المخصصة على صور JPEG باستخدام`ImageSaveOptions`. اضبط الخصائص مثل السطوع والتباين والدقة. على سبيل المثال، لتغيير السطوع إلى 0.3 والتباين إلى 0.7، استخدم هذا الرمز:

```java
options.setImageBrightness(0.3f);
options.setImageContrast(0.7f);
```

### كيف يمكنني استخدام رد الاتصال لتخصيص حفظ الصور؟

 لاستخدام رد الاتصال لتخصيص حفظ الصورة، قم بتعيين`PageSavingCallback` في`ImageSaveOptions` . قم بإنشاء فئة تنفذ`IPageSavingCallback` الواجهة وتجاوز`pageSaving` طريقة.

```java
imageSaveOptions.setPageSavingCallback(new HandlePageSavingCallback());
```

 ثم قم بإنشاء فئة تنفذ`IPageSavingCallback` الواجهة وتخصيص اسم الملف وموقعه في ملف`pageSaving` طريقة.

```java
private static class HandlePageSavingCallback implements IPageSavingCallback {
    public void pageSaving(PageSavingArgs args) {
        args.setPageFileName(MessageFormat.format("Your Directory Path" + "Page_{0}.png", args.getPageIndex()));
    }
}
```