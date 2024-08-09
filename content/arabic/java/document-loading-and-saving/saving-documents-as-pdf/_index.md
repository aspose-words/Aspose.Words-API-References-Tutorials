---
title: حفظ المستندات بصيغة PDF في Aspose.Words لـ Java
linktitle: حفظ المستندات بصيغة PDF
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية حفظ مستندات Word بصيغة PDF باستخدام Aspose.Words لـ Java. تخصيص الخطوط والخصائص وجودة الصورة. دليل شامل لتحويل PDF.
type: docs
weight: 22
url: /ar/java/document-loading-and-saving/saving-documents-as-pdf/
---

## مقدمة لحفظ المستندات بصيغة PDF في Aspose.Words لـ Java

في هذا الدليل التفصيلي، سنستكشف كيفية حفظ المستندات بتنسيق PDF باستخدام Aspose.Words for Java. سنغطي الجوانب المختلفة لتحويل PDF ونقدم أمثلة التعليمات البرمجية لتسهيل العملية.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Words لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).

## تحويل مستند إلى PDF

لتحويل مستند Word إلى PDF، يمكنك استخدام مقتطف التعليمات البرمجية التالي:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 يستبدل`"input.docx"` مع المسار إلى مستند Word الخاص بك و`"output.pdf"` مع مسار ملف PDF الناتج المطلوب.

## التحكم في خيارات حفظ PDF

 يمكنك التحكم في خيارات حفظ PDF المختلفة باستخدام`PdfSaveOptions` فصل. على سبيل المثال، يمكنك تعيين عنوان العرض لمستند PDF على النحو التالي:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## تضمين الخطوط في PDF

لتضمين الخطوط في ملف PDF الذي تم إنشاؤه، استخدم الكود التالي:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## تخصيص خصائص الوثيقة

يمكنك تخصيص خصائص المستند في ملف PDF الذي تم إنشاؤه. على سبيل المثال:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## تصدير هيكل الوثيقة

 لتصدير بنية المستند، قم بتعيين`exportDocumentStructure` خيار ل`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## ضغط الصور

يمكنك التحكم في ضغط الصور باستخدام الكود التالي:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## تحديث آخر خاصية مطبوعة

لتحديث خاصية "آخر طباعة" في ملف PDF، استخدم:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## تقديم تأثيرات DML 3D

للحصول على عرض متقدم لتأثيرات DML ثلاثية الأبعاد، قم بتعيين وضع العرض:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## استيفاء الصور

يمكنك تمكين استيفاء الصورة لتحسين جودة الصورة:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## خاتمة

يوفر Aspose.Words for Java إمكانات شاملة لتحويل مستندات Word إلى تنسيق PDF مع خيارات المرونة والتخصيص. يمكنك التحكم في الجوانب المختلفة لمخرجات PDF، بما في ذلك الخطوط وخصائص المستند وضغط الصور والمزيد.

## الأسئلة الشائعة

### كيف يمكنني تحويل مستند Word إلى PDF باستخدام Aspose.Words لـ Java؟

لتحويل مستند Word إلى PDF استخدم الكود التالي:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 يستبدل`"input.docx"` مع المسار إلى مستند Word الخاص بك و`"output.pdf"` مع مسار ملف PDF الناتج المطلوب.

### هل يمكنني تضمين الخطوط في ملف PDF الذي تم إنشاؤه بواسطة Aspose.Words لـ Java؟

 نعم، يمكنك تضمين الخطوط في ملف PDF عن طريق ضبط الإعداد`setEmbedFullFonts` خيار ل`true` في`PdfSaveOptions`. هنا مثال:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### كيف يمكنني تخصيص خصائص المستند في ملف PDF الذي تم إنشاؤه؟

 يمكنك تخصيص خصائص المستند في ملف PDF باستخدام`setCustomPropertiesExport` الخيار في`PdfSaveOptions`. على سبيل المثال:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### ما هو الغرض من ضغط الصور في Aspose.Words لـ Java؟

 يتيح لك ضغط الصور التحكم في جودة وحجم الصور في ملف PDF الذي تم إنشاؤه. يمكنك ضبط وضع ضغط الصورة باستخدام`setImageCompression` في`PdfSaveOptions`.

### كيف أقوم بتحديث خاصية "آخر طباعة" في ملف PDF؟

 يمكنك تحديث خاصية "آخر طباعة" في ملف PDF عن طريق الإعداد`setUpdateLastPrintedProperty` ل`true` في`PdfSaveOptions`. سيعكس هذا تاريخ الطباعة الأخير في البيانات التعريفية لملف PDF.

### كيف يمكنني تحسين جودة الصورة عند التحويل إلى PDF؟

 لتحسين جودة الصورة، قم بتمكين استيفاء الصورة عن طريق الإعداد`setInterpolateImages` ل`true` في`PdfSaveOptions`. سيؤدي ذلك إلى الحصول على صور أكثر سلاسة وجودة أعلى في ملف PDF.