---
title: استخدام الحواشي السفلية والتعليقات الختامية في Aspose.Words لـ Java
linktitle: استخدام الحواشي السفلية والتعليقات الختامية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعلم كيفية استخدام الحواشي السفلية والتعليقات الختامية بشكل فعال في Aspose.Words لـ Java. عزز مهاراتك في تنسيق المستندات اليوم!
type: docs
weight: 13
url: /ar/java/using-document-elements/using-footnotes-and-endnotes/
---

في هذا البرنامج التعليمي، سنرشدك خلال عملية استخدام الحواشي السفلية والتعليقات الختامية في Aspose.Words for Java. تعد الحواشي السفلية والتعليقات الختامية عناصر أساسية في تنسيق المستند، وغالبًا ما تستخدم للاستشهادات والمراجع والمعلومات الإضافية. يوفر Aspose.Words for Java وظائف قوية للعمل مع الحواشي السفلية والتعليقات الختامية بسلاسة.

## 1. مقدمة إلى الحواشي السفلية والتعليقات الختامية

الحواشي السفلية والتعليقات الختامية هي تعليقات توضيحية توفر معلومات أو اقتباسات تكميلية داخل المستند. تظهر الحواشي السفلية في أسفل الصفحة، بينما يتم جمع التعليقات الختامية في نهاية القسم أو المستند. يتم استخدامها بشكل شائع في الأوراق الأكاديمية والتقارير والمستندات القانونية للإشارة إلى المصادر أو توضيح المحتوى.

## 2. إعداد البيئة الخاصة بك

قبل أن نتعمق في العمل مع الحواشي السفلية والتعليقات الختامية، تحتاج إلى إعداد بيئة التطوير الخاصة بك. تأكد من تثبيت Aspose.Words for Java API وتكوينها في مشروعك.

## 3. إضافة الحواشي السفلية إلى المستند الخاص بك

لإضافة الحواشي السفلية إلى المستند، اتبع الخطوات التالية:
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

public void getFootnoteOptions(){
    Document doc = new Document(dataDir + "Document.docx");
    
    // حدد عدد الأعمدة التي يتم تنسيق منطقة الحواشي السفلية بها.
    doc.getFootnoteOptions().setColumns(3);
    doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
}
```

## 4. تعديل خيارات الحواشي السفلية

يمكنك تعديل خيارات الحواشي السفلية لتخصيص مظهرها وسلوكها. إليك الطريقة:
```java
@Test
public void setFootnoteAndEndNotePosition() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    
    doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
    doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
}
```

## 5. إضافة الحواشي الختامية إلى المستند الخاص بك

تعد إضافة التعليقات الختامية إلى المستند أمرًا بسيطًا. هنا مثال:
```java
@Test
public void setEndnoteOptions() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    DocumentBuilder builder = new DocumentBuilder(doc);
    
    builder.write("Some text");
    builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
    
    EndnoteOptions option = doc.getEndnoteOptions();
    option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
    option.setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
}
```

## 6. تخصيص إعدادات التعليق الختامي

يمكنك أيضًا تخصيص إعدادات التعليقات الختامية لتلبية متطلبات المستند الخاصة بك.

## كود المصدر الكامل
```java
	string dataDir = "Your Document Directory";
	string outPath = "Your Output Directory";
	public void getFootnoteOptions(){
        Document doc = new Document(dataDir + "Document.docx");
        // حدد عدد الأعمدة التي يتم تنسيق منطقة الحواشي السفلية بها.
        doc.getFootnoteOptions().setColumns(3);
        doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
    }
    @Test
    public void setFootnoteAndEndNotePosition() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
        doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
    }
    @Test
    public void setEndnoteOptions() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Some text");
        builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
        EndnoteOptions option = doc.getEndnoteOptions();
        option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
        option.setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
	}
```

## 7. الخاتمة

في هذا البرنامج التعليمي، اكتشفنا كيفية التعامل مع الحواشي السفلية والتعليقات الختامية في Aspose.Words لـ Java. تعتبر هذه الميزات لا تقدر بثمن لإنشاء مستندات جيدة التنظيم مع الاستشهادات والمراجع المناسبة.

الآن بعد أن تعلمت كيفية استخدام الحواشي السفلية والتعليقات الختامية، يمكنك تحسين تنسيق المستند الخاص بك وجعل المحتوى الخاص بك أكثر احترافية.

### أسئلة مكررة

### 1. ما الفرق بين الحواشي السفلية والحواشي الختامية؟
تظهر الحواشي السفلية في أسفل الصفحة، بينما يتم جمع التعليقات الختامية في نهاية القسم أو المستند.

### 2. كيف يمكنني تغيير موضع الحواشي السفلية أو التعليقات الختامية؟
 يمكنك استخدام ال`setPosition` طريقة لتغيير موضع الحواشي السفلية أو التعليقات الختامية.

### 3. هل يمكنني تخصيص تنسيق الحواشي السفلية والتعليقات الختامية؟
نعم، يمكنك تخصيص تنسيق الحواشي السفلية والتعليقات الختامية باستخدام Aspose.Words for Java.

### 4. هل الحواشي السفلية والتعليقات الختامية مهمة في تنسيق المستند؟
نعم، تعد الحواشي السفلية والتعليقات الختامية ضرورية لتوفير المراجع والمعلومات الإضافية في المستندات.

لا تتردد في استكشاف المزيد من ميزات Aspose.Words for Java وتحسين قدرات إنشاء المستندات لديك. ترميز سعيد!