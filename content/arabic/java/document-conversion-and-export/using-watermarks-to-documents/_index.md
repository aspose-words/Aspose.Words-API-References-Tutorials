---
title: استخدام العلامات المائية للمستندات في Aspose.Words لـ Java
linktitle: استخدام العلامات المائية للمستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية إضافة علامات مائية إلى المستندات في Aspose.Words for Java. قم بتخصيص العلامات المائية النصية والصورية للحصول على مستندات ذات مظهر احترافي.
type: docs
weight: 15
url: /ar/java/document-conversion-and-export/using-watermarks-to-documents/
---

## مقدمة لإضافة علامات مائية إلى المستندات في Aspose.Words لـ Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية إضافة علامات مائية إلى المستندات باستخدام Aspose.Words for Java API. تعد العلامات المائية طريقة مفيدة لتسمية المستندات بنصوص أو رسومات للإشارة إلى حالتها أو سريتها أو غيرها من المعلومات ذات الصلة. سنغطي العلامات المائية النصية والصورية في هذا الدليل.

## إعداد Aspose.Words لجافا

قبل أن نبدأ بإضافة العلامات المائية إلى المستندات، نحتاج إلى إعداد Aspose.Words لـ Java. اتبع هذه الخطوات للبدء:

1.  قم بتنزيل Aspose.Words لـ Java من[هنا](https://releases.aspose.com/words/java/).
2. قم بإضافة مكتبة Aspose.Words for Java إلى مشروع Java الخاص بك.
3. قم باستيراد الفئات الضرورية في كود Java الخاص بك.

الآن بعد أن انتهينا من إعداد المكتبة، فلنتابع إضافة العلامات المائية.

## إضافة علامات مائية نصية

تعد العلامات المائية النصية خيارًا شائعًا عندما تريد إضافة معلومات نصية إلى مستنداتك. إليك كيفية إضافة علامة مائية نصية باستخدام Aspose.Words لـ Java:

```java
//إنشاء مثيل مستند
Document doc = new Document("Document.docx");

// تحديد خيارات العلامة المائية النصية
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// اضبط نص العلامة المائية وخياراتها
doc.getWatermark().setText("Test", options);

// احفظ المستند بالعلامة المائية
doc.save("DocumentWithWatermark.docx");
```

## إضافة علامات مائية للصورة

بالإضافة إلى العلامات المائية النصية، يمكنك أيضًا إضافة علامات مائية مصورة إلى مستنداتك. إليك كيفية إضافة علامة مائية للصورة:

```java
//إنشاء مثيل مستند
Document doc = new Document("Document.docx");

// قم بتحميل الصورة للعلامة المائية
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// اضبط حجم العلامة المائية وموضعها
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// أضف العلامة المائية إلى المستند
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// احفظ المستند بالعلامة المائية
doc.save("DocumentWithImageWatermark.docx");
```

## تخصيص العلامات المائية

يمكنك تخصيص العلامات المائية عن طريق ضبط مظهرها وموضعها. بالنسبة للعلامات المائية النصية، يمكنك تغيير الخط والحجم واللون والتخطيط. بالنسبة للعلامات المائية للصور، يمكنك تعديل حجمها وموضعها كما هو موضح في الأمثلة السابقة.

## إزالة العلامات المائية

لإزالة العلامات المائية من مستند، يمكنك استخدام الكود التالي:

```java
//إنشاء مثيل مستند
Document doc = new Document("DocumentWithWatermark.docx");

// قم بإزالة العلامة المائية
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// احفظ المستند بدون العلامة المائية
doc.save("DocumentWithoutWatermark.docx");
```


## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية إضافة علامات مائية إلى المستندات باستخدام Aspose.Words for Java. سواء كنت بحاجة إلى إضافة علامات مائية نصية أو صورية، فإن Aspose.Words يوفر الأدوات اللازمة لتخصيصها وإدارتها بكفاءة. يمكنك أيضًا إزالة العلامات المائية عندما لا تكون هناك حاجة إليها، مما يضمن أن مستنداتك نظيفة واحترافية.

## الأسئلة الشائعة

### كيف يمكنني تغيير خط العلامة المائية النصية؟

 لتغيير خط العلامة المائية النصية، قم بتعديل`setFontFamily` الممتلكات في`TextWatermarkOptions`. على سبيل المثال:

```java
options.setFontFamily("Times New Roman");
```

### هل يمكنني إضافة علامات مائية متعددة إلى مستند واحد؟

 نعم، يمكنك إضافة علامات مائية متعددة إلى المستند عن طريق إنشاء علامات مائية متعددة`Shape` كائنات بإعدادات مختلفة وإضافتها إلى المستند.

### هل من الممكن تدوير العلامة المائية؟

 نعم، يمكنك تدوير العلامة المائية عن طريق ضبط`setRotation` الممتلكات في`Shape` هدف. تقوم القيم الموجبة بتدوير العلامة المائية في اتجاه عقارب الساعة، بينما تقوم القيم السالبة بتدويرها عكس اتجاه عقارب الساعة.

### كيف يمكنني جعل العلامة المائية شبه شفافة؟

 لجعل العلامة المائية شبه شفافة، قم بتعيين`setSemitransparent`الملكية ل`true` في ال`TextWatermarkOptions`.

### هل يمكنني إضافة علامات مائية إلى أقسام معينة من المستند؟

نعم، يمكنك إضافة علامات مائية إلى أقسام معينة من المستند عن طريق التكرار عبر الأقسام وإضافة العلامة المائية إلى الأقسام المطلوبة.