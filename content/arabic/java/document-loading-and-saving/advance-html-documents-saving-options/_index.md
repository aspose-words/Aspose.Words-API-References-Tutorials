---
title: خيارات حفظ مستندات HTML المتقدمة باستخدام Aspose.Words Java
linktitle: حفظ مستندات HTML باستخدام
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: في هذا البرنامج التعليمي، قمنا بتغطية العديد من خيارات حفظ مستندات HTML المتقدمة باستخدام Aspose.Words for Java. تمكنك هذه الخيارات من إنشاء HTML عالي الجودة.
type: docs
weight: 16
url: /ar/java/document-loading-and-saving/advance-html-documents-saving-options/
---

في هذا البرنامج التعليمي، سنستكشف خيارات حفظ مستندات HTML المتقدمة التي يوفرها Aspose.Words لـ Java. Aspose.Words عبارة عن واجهة برمجة تطبيقات Java قوية للعمل مع مستندات Word، وهي توفر نطاقًا واسعًا من الميزات لمعالجة المستندات وتحويلها.

## 1 المقدمة
يتيح لك Aspose.Words for Java العمل مع مستندات Word برمجيًا. في هذا البرنامج التعليمي، سنركز على خيارات حفظ مستندات HTML المتقدمة، والتي تمكنك من التحكم في كيفية تحويل مستندات Word إلى HTML.

## 2. تصدير معلومات رحلة الذهاب والإياب
 ال`exportRoundtripInformation` تسمح لك الطريقة بتصدير مستندات Word إلى HTML مع الحفاظ على معلومات رحلة الذهاب والإياب. يمكن أن تكون هذه المعلومات مفيدة عندما تريد تحويل HTML مرة أخرى إلى تنسيق Word دون فقدان أي تفاصيل خاصة بالمستند.

```java
public void exportRoundtripInformation() throws Exception {
    Document doc = new Document("Your Directory Path" + "Rendering.docx");
    HtmlSaveOptions saveOptions = new HtmlSaveOptions();
    saveOptions.setExportRoundtripInformation(true);
    doc.save("Your Directory Path" + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
}
```

## 3. تصدير الخطوط كـ Base64
 مع ال`exportFontsAsBase64` بهذه الطريقة، يمكنك تصدير الخطوط المستخدمة في المستند كبيانات مشفرة بـ Base64 في HTML. يضمن هذا أن يحتفظ تمثيل HTML بنفس أنماط الخطوط الموجودة في مستند Word الأصلي.

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
 ال`exportResources` تسمح لك هذه الطريقة بتحديد نوع ورقة أنماط CSS وتصدير موارد الخط. يمكنك أيضًا تعيين مجلد موارد واسم مستعار للموارد في HTML.

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
 ال`convertMetafilesToEmfOrWmf`تسمح لك هذه الطريقة بتحويل ملفات التعريف الموجودة في المستند إلى تنسيق EMF أو WMF، مما يضمن التوافق والعرض السلس بتنسيق HTML.

```java
@Test
public void convertMetafilesToEmfOrWmf() throws Exception {
    // لم يتم عرض مقتطف الشفرة للإيجاز.
}
```

## 6. تحويل ملفات التعريف إلى SVG
 استخدم ال`convertMetafilesToSvg` طريقة تحويل ملفات التعريف إلى تنسيق SVG. يعد هذا التنسيق مثاليًا لعرض الرسومات المتجهة في مستندات HTML.

```java
@Test
public void convertMetafilesToSvg() throws Exception {
    // لم يتم عرض مقتطف الشفرة للإيجاز.
}
```

## 7. أضف بادئة اسم فئة CSS
 مع ال`addCssClassNamePrefix` الطريقة، يمكنك إضافة بادئة إلى أسماء فئات CSS في HTML المصدر. يساعد هذا في منع التعارضات مع الأنماط الموجودة.

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
 ال`exportCidUrlsForMhtmlResources` يتم استخدام الطريقة عند حفظ المستندات بتنسيق MHTML. يسمح بتصدير عناوين URL لمعرف المحتوى للموارد.

```java
@Test
public void exportCidUrlsForMhtmlResources() throws Exception {
    // لم يتم عرض مقتطف الشفرة للإيجاز.
}
```

## 9. حل أسماء الخطوط
 ال`resolveFontNames` تساعد هذه الطريقة في حل أسماء الخطوط عند حفظ المستندات بتنسيق HTML، مما يضمن عرضًا متسقًا عبر الأنظمة الأساسية المختلفة.

```java
@Test
public void resolveFontNames() throws Exception {
    // لم يتم عرض مقتطف الشفرة للإيجاز.
}
```

## 10. تصدير حقل نموذج إدخال النص كنص
 ال`exportTextInputFormFieldAsText` تقوم الطريقة بتصدير حقول النموذج كنص عادي في HTML، مما يجعلها قابلة للقراءة والتحرير بسهولة.

```java
@Test
public void exportTextInputFormFieldAsText() throws Exception {
    // لم يتم عرض مقتطف الشفرة للإيجاز.
}
```

## 11. الاستنتاج
في هذا البرنامج التعليمي، استكشفنا خيارات حفظ مستندات HTML المتقدمة التي يوفرها Aspose.Words لـ Java. تمنحك هذه الخيارات تحكمًا دقيقًا في عملية التحويل، مما يسمح لك بإنشاء مستندات HTML تشبه إلى حد كبير مستندات Word الأصلية.

## 12.الأسئلة الشائعة
فيما يلي بعض الأسئلة المتداولة حول العمل مع Aspose.Words لخيارات حفظ مستندات Java وHTML:

### س1: كيف يمكنني تحويل HTML مرة أخرى إلى تنسيق Word باستخدام Aspose.Words لـ Java؟
 لتحويل HTML مرة أخرى إلى تنسيق Word، يمكنك استخدام Aspose.Words API`load` طريقة لتحميل مستند HTML ثم حفظه بتنسيق Word.

### س2: هل يمكنني تخصيص أنماط CSS عند التصدير إلى HTML؟
 نعم، يمكنك تخصيص أنماط CSS عن طريق تعديل أوراق الأنماط المستخدمة في HTML أو باستخدام`addCssClassNamePrefix` طريقة لإضافة بادئة إلى أسماء فئات CSS.

### س3: هل توجد طريقة لتحسين مخرجات HTML لعرضها على الويب؟
نعم، يمكنك تحسين إخراج HTML لعرض الويب عن طريق تكوين خيارات مثل تصدير الخطوط كـ Base64 وتحويل ملفات التعريف إلى SVG.

### س 4: هل توجد أية قيود عند تحويل مستندات Word المعقدة إلى HTML؟
في حين أن Aspose.Words for Java يوفر إمكانات تحويل قوية، فإن مستندات Word المعقدة ذات التخطيطات المعقدة قد تتطلب معالجة لاحقة إضافية لتحقيق مخرجات HTML المطلوبة.
