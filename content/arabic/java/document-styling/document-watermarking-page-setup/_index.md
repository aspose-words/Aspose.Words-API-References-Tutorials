---
title: العلامة المائية للوثيقة وإعداد الصفحة
linktitle: العلامة المائية للوثيقة وإعداد الصفحة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية تطبيق العلامات المائية وإعداد تكوينات الصفحة باستخدام Aspose.Words for Java. دليل شامل مع كود المصدر.
type: docs
weight: 13
url: /ar/java/document-styling/document-watermarking-page-setup/
---
## مقدمة

في مجال معالجة المستندات، يمثل Aspose.Words for Java أداة قوية، مما يسمح للمطورين بالتحكم في كل جانب من جوانب معالجة المستندات. في هذا الدليل الشامل، سنتعمق في تعقيدات وضع العلامات المائية على المستندات وإعداد الصفحة باستخدام Aspose.Words for Java. سواء كنت مطورًا متمرسًا أو مجرد دخول إلى عالم معالجة مستندات Java، فإن هذا الدليل خطوة بخطوة سيزودك بالمعرفة وكود المصدر الذي تحتاجه.

## العلامة المائية للوثيقة

### إضافة علامات مائية

يمكن أن تكون إضافة العلامات المائية إلى المستندات أمرًا ضروريًا للعلامة التجارية أو تأمين المحتوى الخاص بك. Aspose.Words for Java يجعل هذه المهمة واضحة. وإليك الطريقة:

```java
// قم بتحميل المستند
Document doc = new Document("document.docx");

// إنشاء علامة مائية
Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.getTextPath().setText("Confidential");
watermark.setWidth(300);
watermark.setHeight(100);

// ضع العلامة المائية
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.setWrapType(WrapType.NONE);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);

// أدخل العلامة المائية
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// احفظ المستند
doc.save("document_with_watermark.docx");
```

### تخصيص العلامات المائية

يمكنك تخصيص العلامات المائية بشكل أكبر عن طريق ضبط الخط والحجم واللون والتدوير. تضمن هذه المرونة أن العلامة المائية الخاصة بك تتوافق مع نمط المستند الخاص بك بسلاسة.

## إعداد الصفحة

### حجم الصفحة والاتجاه

يعد إعداد الصفحة أمرًا محوريًا في تنسيق المستند. يوفر Aspose.Words for Java تحكمًا كاملاً في حجم الصفحة واتجاهها:

```java
// قم بتحميل المستند
Document doc = new Document("document.docx");

// اضبط حجم الصفحة على A4
doc.getFirstSection().getPageSetup().setPageWidth(595.0);
doc.getFirstSection().getPageSetup().setPageHeight(842.0);

// تغيير اتجاه الصفحة إلى أفقي
doc.getFirstSection().getPageSetup().setOrientation(Orientation.LANDSCAPE);

// احفظ المستند المعدل
doc.save("formatted_document.docx");
```

### الهوامش وترقيم الصفحات

يعد التحكم الدقيق في الهوامش وترقيم الصفحات أمرًا ضروريًا للمستندات الاحترافية. يمكنك تحقيق ذلك باستخدام Aspose.Words لـ Java:

```java
// قم بتحميل المستند
Document doc = new Document("document.docx");

// تعيين الهوامش
doc.getFirstSection().getPageSetup().setLeftMargin(72.0);
doc.getFirstSection().getPageSetup().setRightMargin(72.0);
doc.getFirstSection().getPageSetup().setTopMargin(72.0);
doc.getFirstSection().getPageSetup().setBottomMargin(72.0);

// تمكين ترقيم الصفحات
doc.getFirstSection().getPageSetup().setDifferentFirstPageHeaderFooter(true);
HeaderFooter firstPageHeader = doc.getFirstSection().getHeadersFooters().getByHeaderFooterType(HeaderFooterType.HEADER_FIRST);
firstPageHeader.appendParagraph("First Page Header");

// احفظ المستند المنسق
doc.save("formatted_document.docx");
```

## الأسئلة الشائعة

### كيف يمكنني إزالة علامة مائية من مستند؟

لإزالة علامة مائية من مستند، يمكنك التنقل بين أشكال المستند وإزالة الأشكال التي تمثل علامات مائية. إليك مقتطف:

```java
Document doc = new Document("document_with_watermark.docx");

for (Shape shape : doc.getChildNodes(NodeType.SHAPE, true).<Shape>toArray()) {
    if (shape.getText().contains("Confidential")) {
        shape.remove();
    }
}

doc.save("document_without_watermark.docx");
```

### هل يمكنني إضافة علامات مائية متعددة إلى مستند واحد؟

نعم، يمكنك إضافة علامات مائية متعددة إلى مستند عن طريق إنشاء كائنات أشكال إضافية وتحديد موضعها حسب الحاجة.

### كيف يمكنني تغيير حجم الصفحة إلى قانوني في الاتجاه الأفقي؟

لتعيين حجم الصفحة إلى قانوني في الاتجاه الأفقي، قم بتعديل عرض الصفحة وارتفاعها كما يلي:

```java
doc.getFirstSection().getPageSetup().setPageWidth(842.0);
doc.getFirstSection().getPageSetup().setPageHeight(595.0);
```

### ما هو الخط الافتراضي للعلامات المائية؟

الخط الافتراضي للعلامات المائية هو Calibri بحجم خط 36.

### كيف يمكنني إضافة أرقام الصفحات بدءاً من صفحة معينة؟

يمكنك تحقيق ذلك عن طريق تعيين رقم صفحة البداية في مستندك على النحو التالي:

```java
doc.getFirstSection().getPageSetup().setPageStartingNumber(5);
```

### كيف أقوم بمحاذاة النص إلى المنتصف في الرأس أو التذييل؟

يمكنك محاذاة النص إلى المنتصف في الرأس أو التذييل باستخدام الأسلوب setAlignment على كائن الفقرة داخل الرأس أو التذييل.

## خاتمة

في هذا الدليل الشامل، اكتشفنا فن وضع العلامات المائية على المستندات وإعداد الصفحة باستخدام Aspose.Words for Java. مسلحًا بمقتطفات ورؤى التعليمات البرمجية المصدر المتوفرة، لديك الآن الأدوات اللازمة للتعامل مع مستنداتك وتنسيقها ببراعة. يمكّنك Aspose.Words for Java من إنشاء مستندات احترافية ذات علامة تجارية مصممة وفقًا لمواصفاتك الدقيقة.

يعد إتقان التعامل مع المستندات مهارة قيمة للمطورين، وAspose.Words for Java هو رفيقك الموثوق به في هذه الرحلة. ابدأ في إنشاء مستندات مذهلة اليوم!