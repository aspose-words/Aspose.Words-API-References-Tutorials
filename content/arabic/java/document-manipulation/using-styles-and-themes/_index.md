---
title: استخدام الأنماط والسمات في Aspose.Words لـ Java
linktitle: استخدام الأنماط والموضوعات
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية تحسين تنسيق المستندات باستخدام Aspose.Words لـ Java. استكشف الأنماط والموضوعات والمزيد في هذا الدليل الشامل مع أمثلة التعليمات البرمجية المصدر.
type: docs
weight: 20
url: /ar/java/document-manipulation/using-styles-and-themes/
---

## مقدمة لاستخدام الأنماط والسمات في Aspose.Words لـ Java

في هذا الدليل، سنستكشف كيفية العمل مع الأنماط والموضوعات في Aspose.Words for Java لتحسين تنسيق مستنداتك ومظهرها. سنغطي موضوعات مثل استرداد الأنماط، ونسخ الأنماط، وإدارة السمات، وإدراج فواصل الأنماط. دعونا نبدأ!

## استرجاع الأنماط

لاسترداد الأنماط من مستند، يمكنك استخدام مقتطف كود Java التالي:

```java
Document doc = new Document();
String styleName = "";
//احصل على مجموعة الأنماط من المستند.
StyleCollection styles = doc.getStyles();
for (Style style : styles)
{
    if ("".equals(styleName))
    {
        styleName = style.getName();
        System.out.println(styleName);
    }
    else
    {
        styleName = styleName + ", " + style.getName();
        System.out.println(styleName);
    }
}
```

يقوم هذا الرمز بجلب الأنماط المحددة في المستند وطباعة أسمائها.

## أنماط النسخ

 لنسخ الأنماط من مستند إلى آخر، يمكنك استخدام`copyStylesFromTemplate` الطريقة كما هو موضح أدناه:

```java
@Test
public void copyStyles() throws Exception
{
    Document doc = new Document();
    Document target = new Document("Your Directory Path" + "Rendering.docx");
    target.copyStylesFromTemplate(doc);
    doc.save("Your Directory Path" + "WorkingWithStylesAndThemes.CopyStyles.docx");
}
```

يقوم هذا الرمز بنسخ الأنماط من مستند القالب إلى المستند الحالي.

## إدارة المواضيع

تعتبر السمات ضرورية لتحديد المظهر العام للمستند الخاص بك. يمكنك استرداد وتعيين خصائص السمة كما هو موضح في الكود التالي:

```java
@Test
public void getThemeProperties() throws Exception
{
    Document doc = new Document();
    Theme theme = doc.getTheme();
    System.out.println(theme.getMajorFonts().getLatin());
    System.out.println(theme.getMinorFonts().getEastAsian());
    System.out.println(theme.getColors().getAccent1());
}

@Test
public void setThemeProperties() throws Exception
{
    Document doc = new Document();
    Theme theme = doc.getTheme();
    theme.getMinorFonts().setLatin("Times New Roman");
    theme.getColors().setHyperlink(Color.ORANGE);
}
```

توضح هذه المقتطفات كيفية استرداد خصائص السمة وتعديلها، مثل الخطوط والألوان.

## إدراج فواصل النمط

تعتبر فواصل الأنماط مفيدة لتطبيق أنماط مختلفة ضمن فقرة واحدة. فيما يلي مثال لكيفية إدراج فواصل الأنماط:

```java
@Test
public void insertStyleSeparator() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    Style paraStyle = builder.getDocument().getStyles().add(StyleType.PARAGRAPH, "MyParaStyle");
    paraStyle.getFont().setBold(false);
    paraStyle.getFont().setSize(8.0);
    paraStyle.getFont().setName("Arial");
    // إلحاق نص بنمط "العنوان 1".
    builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);
    builder.write("Heading 1");
    builder.insertStyleSeparator();
    // إلحاق النص بنمط آخر.
    builder.getParagraphFormat().setStyleName(paraStyle.getName());
    builder.write("This is text with some other formatting ");
    doc.save("Your Directory Path" + "WorkingWithStylesAndThemes.InsertStyleSeparator.docx");
}
```

في هذا الكود، نقوم بإنشاء نمط فقرة مخصص وإدراج فاصل نمط لتبديل الأنماط داخل نفس الفقرة.

## خاتمة

يغطي هذا الدليل أساسيات العمل باستخدام الأنماط والموضوعات في Aspose.Words for Java. لقد تعلمت كيفية استرداد الأنماط ونسخها وإدارة السمات وإدراج فواصل الأنماط لإنشاء مستندات جذابة ومنسقة بشكل جيد. قم بتجربة هذه التقنيات لتخصيص مستنداتك وفقًا لمتطلباتك.


## الأسئلة الشائعة

### كيف يمكنني استرداد خصائص السمات في Aspose.Words لـ Java؟

يمكنك استرداد خصائص السمة عن طريق الوصول إلى كائن السمة وخصائصه.

### كيف يمكنني تعيين خصائص السمة، مثل الخطوط والألوان؟

يمكنك تعيين خصائص السمة عن طريق تعديل خصائص كائن السمة.

### كيف يمكنني استخدام فواصل الأنماط لتبديل الأنماط داخل نفس الفقرة؟

 يمكنك إدراج فواصل الأنماط باستخدام`insertStyleSeparator` طريقة`DocumentBuilder` فصل.