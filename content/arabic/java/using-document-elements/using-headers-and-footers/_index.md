---
title: استخدام الرؤوس والتذييلات في Aspose.Words لـ Java
linktitle: استخدام الرؤوس والتذييلات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرّف خطوة بخطوة على كيفية استخدام الرؤوس والتذييلات في Aspose.Words for Java. قم بإنشاء مستندات احترافية دون عناء.
type: docs
weight: 16
url: /ar/java/using-document-elements/using-headers-and-footers/
---

في هذا الدليل الشامل، سنرشدك خلال عملية التعامل مع الرؤوس والتذييلات في Aspose.Words for Java. تعتبر الرؤوس والتذييلات عناصر أساسية في تنسيق المستندات، ويوفر Aspose.Words أدوات قوية لإنشاءها وتخصيصها وفقًا لاحتياجاتك.

الآن، دعونا نتعمق في كل خطوة من هذه الخطوات بالتفصيل.

## 1. مقدمة إلى Aspose.Words

Aspose.Words عبارة عن واجهة برمجة تطبيقات Java قوية تتيح لك إنشاء مستندات Word ومعالجتها وعرضها برمجيًا. فهو يوفر ميزات واسعة النطاق لتنسيق المستندات، بما في ذلك الرؤوس والتذييلات.

## 2. إعداد بيئة جافا الخاصة بك

 قبل البدء في استخدام Aspose.Words، تأكد من إعداد بيئة تطوير Java لديك بشكل صحيح. يمكنك العثور على تعليمات الإعداد اللازمة على صفحة وثائق Aspose.Words:[Aspose.Words وثائق جافا](https://reference.aspose.com/words/java/).

## 3. إنشاء مستند جديد

للعمل مع الرؤوس والتذييلات، تحتاج إلى إنشاء مستند جديد باستخدام Aspose.Words. يوضح التعليمة البرمجية التالية كيفية القيام بذلك:

```java
// كود جافا لإنشاء مستند جديد
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. فهم إعداد الصفحة

 يعد إعداد الصفحة أمرًا بالغ الأهمية للتحكم في تخطيط المستند. يمكنك تحديد خصائص متنوعة تتعلق بالرؤوس والتذييلات باستخدام الملف`PageSetup` فصل. على سبيل المثال:

```java
// إعداد خصائص الصفحة
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. رأس/تذييل مختلف للصفحة الأولى

يتيح لك Aspose.Words الحصول على رؤوس وتذييلات مختلفة للصفحة الأولى من المستند. يستخدم`pageSetup.setDifferentFirstPageHeaderFooter(true);` لتمكين هذه الميزة.

## 6. العمل مع الرؤوس

### 6.1. إضافة نص إلى الرؤوس

 يمكنك إضافة نص إلى الرؤوس باستخدام`DocumentBuilder`. هنا مثال:

```java
// إضافة نص إلى رأس الصفحة الأولى
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. إدراج الصور في الرؤوس

 لإدراج الصور في الرؤوس، يمكنك استخدام`insertImage` طريقة. هنا مثال:

```java
// إدراج صورة في الرأس
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. تخصيص أنماط الرأس

يمكنك تخصيص أنماط الرأس عن طريق تعيين خصائص مختلفة مثل الخط والمحاذاة والمزيد، كما هو موضح في الأمثلة أعلاه.

## 7. العمل مع التذييلات

### 7.1. إضافة نص إلى التذييلات

 كما هو الحال مع الرؤوس، يمكنك إضافة نص إلى التذييلات باستخدام الزر`DocumentBuilder`. هنا مثال:

```java
// إضافة نص إلى التذييل الأساسي
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// أدخل النص والحقول حسب الحاجة
```

### 7.2. إدراج الصور في التذييلات

 لإدراج الصور في التذييلات، استخدم`insertImage` الطريقة، تماما كما هو الحال في الرؤوس.

### 7.3. تخصيص أنماط التذييل

 تخصيص أنماط التذييل باستخدام`DocumentBuilder`، على غرار تخصيص الرؤوس.

## 8. ترقيم الصفحات

 يمكنك تضمين أرقام الصفحات في الرؤوس والتذييلات باستخدام حقول مثل`PAGE` و`NUMPAGES`. يتم تحديث هذه الحقول تلقائيًا عند إضافة صفحات أو إزالتها.

## 9. معلومات حقوق النشر في التذييلات

لإضافة معلومات حقوق الطبع والنشر إلى تذييل المستند، يمكنك استخدام جدول يحتوي على خليتين، بمحاذاة إحداهما إلى اليسار والأخرى إلى اليمين، كما هو موضح في مقتطف الشفرة.

## 10. العمل مع أقسام متعددة

يتيح لك Aspose.Words العمل مع أقسام متعددة داخل المستند. يمكنك تعيين إعدادات مختلفة للصفحة ورؤوس/تذييلات لكل قسم.

## 11. التوجه نحو المناظر الطبيعية

يمكنك تغيير اتجاه أقسام معينة إلى الوضع الأفقي إذا لزم الأمر.

## 12. نسخ الرؤوس والتذييلات من الأقسام السابقة

يمكن أن يؤدي نسخ الرؤوس والتذييلات من الأقسام السابقة إلى توفير الوقت عند إنشاء مستندات معقدة.

## 13. حفظ المستند الخاص بك

بعد إنشاء المستند وتخصيصه، لا تنس حفظه باستخدام الملف`doc.save()` طريقة.

## كود المصدر الكامل
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // حدد ما إذا كنا نريد أن تكون رؤوس/تذييلات الصفحة الأولى مختلفة عن الصفحات الأخرى.
        // يمكنك أيضًا استخدام خاصية PageSetup.OddAndEvenPagesHeaderFooter للتحديد
        // رؤوس/تذييلات مختلفة للصفحات الفردية والزوجية.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // قم بإدراج صورة موضوعة في الزاوية العلوية/اليسرى من الرأس.
        // يتم ضبط المسافة من الحواف العلوية/اليسرى للصفحة على 10 نقاط.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // نستخدم جدولاً يحتوي على خليتين لإنشاء جزء واحد من النص على السطر (مع ترقيم الصفحات).
        // تتم محاذاته إلى اليسار، ومحاذاة الجزء الآخر من النص (مع حقوق الطبع والنشر) إلى اليمين.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // ويستخدم حقول PAGE وNUMPAGES لحساب رقم الصفحة الحالية والعديد من الصفحات تلقائيًا.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // قم بعمل فاصل صفحات لإنشاء صفحة ثانية تظهر عليها الرؤوس والتذييلات الأساسية.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // لا يحتاج هذا القسم إلى رأس/تذييل مختلف للصفحة الأولى، فنحن نحتاج فقط إلى صفحة عنوان واحدة في المستند،
        //وقد تم بالفعل تحديد رأس/تذييل هذه الصفحة في القسم السابق.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // يعرض هذا القسم الرؤوس/التذييلات من القسم السابق
        // بشكل افتراضي، قم باستدعاء currentSection.HeadersFooters.LinkToPrevious(false) لإلغاء عرض الصفحة هذا
        // يختلف بالنسبة للقسم الجديد، وبالتالي نحتاج إلى تعيين عروض مختلفة للخلايا لجدول التذييل.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // إذا أردنا استخدام مجموعة الرأس/التذييل الموجودة بالفعل لهذا القسم.
        // ولكن مع بعض التعديلات الطفيفة، قد يكون من المناسب نسخ الرؤوس/التذييلات
        // من القسم السابق وتطبيق التعديلات اللازمة حيث نريدها.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
الكود المصدري لأسلوب CopyHeadersFootersFromPreviousSection
```java
    /// <الملخص>
    /// النسخ ونسخ الرؤوس والتذييلات من القسم السابق إلى القسم المحدد.
    /// </ملخص>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## خاتمة

في هذا البرنامج التعليمي، قمنا بتغطية أساسيات العمل باستخدام الرؤوس والتذييلات في Aspose.Words لـ Java. لقد تعلمت كيفية إنشاء الرؤوس والتذييلات وتخصيصها وتصميمها، بالإضافة إلى تقنيات تنسيق المستندات الأساسية الأخرى.

 لمزيد من التفاصيل والميزات المتقدمة، راجع[Aspose.Words وثائق جافا](https://reference.aspose.com/words/java/).

## الأسئلة الشائعة

### 1. كيف يمكنني إضافة أرقام الصفحات إلى تذييل المستند الخاص بي؟
 يمكنك إضافة أرقام الصفحات عن طريق إدراج`PAGE` الحقل في التذييل باستخدام Aspose.Words.

### 2. هل Aspose.Words متوافق مع بيئات تطوير Java؟
نعم، يوفر Aspose.Words الدعم لتطوير Java. تأكد من أن لديك الإعداد اللازم في مكانه.

### 3. هل يمكنني تخصيص الخط ونمط الرؤوس والتذييلات؟
بالتأكيد، يمكنك تخصيص الخطوط والمحاذاة والأنماط الأخرى لجعل الرؤوس والتذييلات جذابة بصريًا.

### 4. هل من الممكن أن يكون هناك رؤوس مختلفة للصفحات الفردية والزوجية؟
 نعم، يمكنك استخدام`PageSetup.OddAndEvenPagesHeaderFooter` لتحديد رؤوس مختلفة للصفحات الفردية والزوجية.

### 5. كيف أبدأ باستخدام Aspose.Words لـ Java؟
 للبدء، قم بزيارة[Aspose.Words وثائق جافا](https://reference.aspose.com/words/java/) للحصول على إرشادات شاملة حول استخدام واجهة برمجة التطبيقات.