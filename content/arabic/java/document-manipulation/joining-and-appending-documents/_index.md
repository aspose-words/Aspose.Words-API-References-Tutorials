---
title: ضم المستندات وإلحاقها في Aspose.Words لـ Java
linktitle: الانضمام وإلحاق المستندات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية ضم المستندات وإلحاقها بسهولة باستخدام Aspose.Words for Java. الحفاظ على التنسيق وإدارة الرؤوس والتذييلات والمزيد.
type: docs
weight: 30
url: /ar/java/document-manipulation/joining-and-appending-documents/
---

## مقدمة لضم المستندات وإلحاقها في Aspose.Words لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية ضم المستندات وإلحاقها باستخدام مكتبة Aspose.Words for Java. ستتعلم كيفية دمج مستندات متعددة بسلاسة مع الحفاظ على التنسيق والبنية.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من إعداد Aspose.Words for Java API في مشروع Java الخاص بك.

## خيارات الانضمام إلى المستندات

### إلحاق بسيط

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### إلحاق مع خيارات تنسيق الاستيراد

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### إلحاق بمستند فارغ

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### إلحاق بتحويلات رقم الصفحة

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // تحويل NUMPAGES من الحقول
dstDoc.updatePageLayout(); // تحديث تخطيط الصفحة للترقيم الصحيح
```

## التعامل مع إعدادات الصفحة المختلفة

عند إلحاق مستندات بإعدادات صفحة مختلفة:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// تأكد من تطابق إعدادات إعداد الصفحة مع المستند الوجهة
```

## ضم المستندات بأنماط مختلفة

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## سلوك النمط الذكي

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## إدراج المستندات باستخدام DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## حفظ ترقيم المصدر

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## التعامل مع مربعات النص

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## إدارة الرؤوس والتذييلات

### ربط الرؤوس والتذييلات

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### إلغاء ربط الرؤوس والتذييلات

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## خاتمة

يوفر Aspose.Words for Java أدوات مرنة وقوية لضم المستندات وإلحاقها، سواء كنت بحاجة إلى الحفاظ على التنسيق أو التعامل مع إعدادات الصفحة المختلفة أو إدارة الرؤوس والتذييلات. قم بتجربة هذه التقنيات لتلبية احتياجاتك المحددة لمعالجة المستندات.

## الأسئلة الشائعة

### كيف يمكنني ضم المستندات ذات الأنماط المختلفة بسلاسة؟

 لضم المستندات ذات الأنماط المختلفة، استخدم`ImportFormatMode.USE_DESTINATION_STYLES` عند الإلحاق.

### هل يمكنني الحفاظ على ترقيم الصفحات عند إلحاق المستندات؟

 نعم، يمكنك الحفاظ على ترقيم الصفحات باستخدام`convertNumPageFieldsToPageRef` طريقة وتحديث تخطيط الصفحة.

### ما هو سلوك النمط الذكي؟

 يساعد سلوك النمط الذكي في الحفاظ على الأنماط المتسقة عند إلحاق المستندات. استخدامه مع`ImportFormatOptions` للحصول على نتائج أفضل.

### كيف يمكنني التعامل مع مربعات النص عند إلحاق المستندات؟

تعيين`importFormatOptions.setIgnoreTextBoxes(false)` لتضمين مربعات النص أثناء الإلحاق.

### ماذا لو كنت أرغب في ربط/إلغاء ربط الرؤوس والتذييلات بين المستندات؟

 يمكنك ربط الرؤوس والتذييلات باستخدام`linkToPrevious(true)` أو فك الارتباط معهم`linkToPrevious(false)` كما هو مطلوب.