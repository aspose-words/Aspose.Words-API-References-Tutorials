---
title: خيارات حفظ مستندات HTML المتقدمة باستخدام Aspose.Words Java
linktitle: حفظ مستندات HTML باستخدام
second_title: واجهة برمجة تطبيقات معالجة المستندات في Java Aspose.Words
description: في هذا البرنامج التعليمي، قمنا بتغطية خيارات حفظ مستندات HTML المتقدمة المختلفة باستخدام Aspose.Words for Java. تمكنك هذه الخيارات من إنشاء مستندات HTML عالية الجودة
type: docs
weight: 16
url: /ar/java/document-loading-and-saving/advance-html-documents-saving-options/
---

في هذا البرنامج التعليمي، سنستكشف خيارات حفظ مستندات HTML المتقدمة التي يوفرها Aspose.Words لـ Java. Aspose.Words عبارة عن واجهة برمجة تطبيقات Java قوية للعمل مع مستندات Word، كما تقدم مجموعة واسعة من الميزات لمعالجة المستندات وتحويلها.

## 1. المقدمة
يتيح لك برنامج Aspose.Words for Java العمل مع مستندات Word برمجيًا. في هذا البرنامج التعليمي، سنركز على خيارات حفظ مستندات HTML المتقدمة، والتي تمكنك من التحكم في كيفية تحويل مستندات Word إلى HTML.

## 2. تصدير معلومات الرحلة ذهابًا وإيابًا
ال`exportRoundtripInformation` تتيح لك هذه الطريقة تصدير مستندات Word إلى HTML مع الحفاظ على معلومات الذهاب والإياب. يمكن أن تكون هذه المعلومات مفيدة عندما تريد تحويل HTML مرة أخرى إلى تنسيق Word دون فقدان أي تفاصيل خاصة بالمستند.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. تصدير الخطوط بتنسيق Base64
 مع`exportFontsAsBase64` باستخدام هذه الطريقة، يمكنك تصدير الخطوط المستخدمة في المستند كبيانات مشفرة بتنسيق Base64 بتنسيق HTML. وهذا يضمن احتفاظ تمثيل HTML بنفس أنماط الخطوط الموجودة في مستند Word الأصلي.

```java
@Test
public void exportFontsAsBase64() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportFontsAsBase64(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
}
```

## 4. تصدير الموارد
ال`exportResources` تتيح لك الطريقة تحديد نوع جدول أنماط CSS وتصدير موارد الخطوط. يمكنك أيضًا تعيين مجلد موارد واسم مستعار للموارد في HTML.

```java
@Test
public void exportResources() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setExportFontResources(true);
    saveOptions.setResourceFolder("Your Directory Path" + "Resources");
    saveOptions.setResourceFolderAlias("http://example.com/resources");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
}
```

## 5. تحويل ملفات التعريف إلى EMF أو WMF
ال`convertMetafilesToEmfOrWmf`تتيح لك الطريقة تحويل ملفات التعريف في المستند إلى تنسيق EMF أو WMF، مما يضمن التوافق والتقديم السلس في HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // لم يتم عرض مقتطف الكود من أجل الاختصار.
}
```

## 6. تحويل ملفات التعريف إلى SVG
 استخدم`convertMetafilesToSvg` طريقة لتحويل ملفات التعريف إلى تنسيق SVG. هذا التنسيق مثالي لعرض الرسومات المتجهة في مستندات HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // لم يتم عرض مقتطف الكود من أجل الاختصار.
}
```

## 7. أضف بادئة اسم فئة CSS
 مع`addCssClassNamePrefix` باستخدام هذه الطريقة، يمكنك إضافة بادئة إلى أسماء فئات CSS في HTML المُصدَّر. يساعد هذا في منع التعارضات مع الأنماط الموجودة.

```java
@Test
public void addCssClassNamePrefix() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setCssStyleSheetType(CssStyleSheetType.EXTERNAL);
    saveOptions.setCssClassNamePrefix("pfx_");
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
}
```

## 8. تصدير عناوين URL الخاصة بـ CID لموارد MHTML
ال`exportCidUrlsForMhtmlResources` تُستخدم هذه الطريقة عند حفظ المستندات بتنسيق MHTML. وهي تسمح بتصدير عناوين URL لمعرف المحتوى للموارد.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // لم يتم عرض مقتطف الكود من أجل الاختصار.
}
```

## 9. حل أسماء الخطوط
ال`resolveFontNames` تساعد الطريقة على حل أسماء الخطوط عند حفظ المستندات بتنسيق HTML، مما يضمن عرضًا متسقًا عبر منصات مختلفة.

```java
@Test
public void resolveFontNames() throws Exception {
    // لم يتم عرض مقتطف الكود من أجل الاختصار.
}
```

## 10. تصدير حقل إدخال النص في النموذج كنص
ال`exportTextInputFormFieldAsText` تصدر الطريقة حقول النموذج كنص عادي في HTML، مما يجعلها قابلة للقراءة والتحرير بسهولة.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // لم يتم عرض مقتطف الكود من أجل الاختصار.
}
```

## 11. الخاتمة
في هذا البرنامج التعليمي، استكشفنا خيارات حفظ مستندات HTML المتقدمة التي يوفرها Aspose.Words for Java. تمنحك هذه الخيارات تحكمًا دقيقًا في عملية التحويل، مما يسمح لك بإنشاء مستندات HTML تشبه إلى حد كبير مستندات Word الأصلية.

## 12. الأسئلة الشائعة
فيما يلي بعض الأسئلة الشائعة حول العمل مع Aspose.Words لخيارات حفظ مستندات Java وHTML:

### س1: كيف يمكنني تحويل HTML إلى تنسيق Word باستخدام Aspose.Words لـ Java؟
 لتحويل HTML إلى تنسيق Word مرة أخرى، يمكنك استخدام واجهة برمجة تطبيقات Aspose.Words`load` طريقة تحميل مستند HTML ثم حفظه بتنسيق Word.

### س2: هل يمكنني تخصيص أنماط CSS عند التصدير إلى HTML؟
 نعم، يمكنك تخصيص أنماط CSS عن طريق تعديل أوراق الأنماط المستخدمة في HTML أو باستخدام`addCssClassNamePrefix` طريقة لإضافة بادئة إلى أسماء فئات CSS.

### س3: هل هناك طريقة لتحسين مخرجات HTML للعرض على الويب؟
نعم، يمكنك تحسين مخرجات HTML لعرضها على الويب من خلال تكوين خيارات مثل تصدير الخطوط بتنسيق Base64 وتحويل الملفات التعريفية إلى SVG.

### س4: هل هناك أية قيود عند تحويل مستندات Word المعقدة إلى HTML؟
على الرغم من أن Aspose.Words for Java يوفر إمكانيات تحويل قوية، إلا أن مستندات Word المعقدة ذات التخطيطات المعقدة قد تتطلب معالجة لاحقة إضافية لتحقيق الناتج HTML المطلوب.
