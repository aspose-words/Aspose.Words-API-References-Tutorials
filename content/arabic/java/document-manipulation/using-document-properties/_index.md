---
title: استخدام خصائص المستند في Aspose.Words لـ Java
linktitle: استخدام خصائص الوثيقة
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: قم بتحسين إدارة المستندات باستخدام Aspose.Words لـ Java. تعلم كيفية التعامل مع خصائص المستند، وإضافة بيانات التعريف المخصصة، والمزيد في هذا البرنامج التعليمي الشامل.
type: docs
weight: 32
url: /ar/java/document-manipulation/using-document-properties/
---

## مقدمة إلى خصائص الوثيقة

تعد خصائص المستند جزءًا حيويًا من أي مستند. وهي توفر معلومات إضافية حول المستند نفسه، مثل العنوان والمؤلف والموضوع والكلمات الرئيسية والمزيد. في Aspose.Words for Java، يمكنك التعامل مع خصائص المستند المضمنة والمخصصة.

## تعداد خصائص الوثيقة

### خصائص مدمجة

لاسترداد خصائص المستند المضمنة والعمل معها، يمكنك استخدام مقتطف التعليمات البرمجية التالي:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

سيعرض هذا الرمز اسم المستند والخصائص المضمنة، بما في ذلك خصائص مثل "العنوان" و"المؤلف" و"الكلمات الأساسية".

### خصائص مخصصة

للعمل مع خصائص المستند المخصصة، يمكنك استخدام مقتطف التعليمات البرمجية التالي:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

يوضح مقتطف التعليمات البرمجية هذا كيفية إضافة خصائص مستند مخصصة، بما في ذلك قيمة منطقية وسلسلة وتاريخ ورقم مراجعة وقيمة رقمية.

## إزالة خصائص الوثيقة

لإزالة خصائص وثيقة معينة، يمكنك استخدام التعليمات البرمجية التالية:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

يقوم هذا الرمز بإزالة الخاصية المخصصة "التاريخ المعتمد" من المستند.

## تكوين الارتباط للمحتوى

في بعض الحالات، قد ترغب في إنشاء روابط داخل المستند الخاص بك. وإليك كيف يمكنك القيام بذلك:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // إضافة مرتبطة بخاصية المحتوى.
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

يوضح مقتطف التعليمات البرمجية هذا كيفية إنشاء إشارة مرجعية في مستندك وإضافة خاصية مستند مخصصة ترتبط بتلك الإشارة المرجعية.

## التحويل بين وحدات القياس

في Aspose.Words for Java، يمكنك تحويل وحدات القياس بسهولة. فيما يلي مثال لكيفية القيام بذلك:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // تعيين الهوامش بالبوصة.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

يقوم مقتطف الكود هذا بتعيين هوامش ومسافات مختلفة بالبوصة عن طريق تحويلها إلى نقاط.

## استخدام أحرف التحكم

يمكن أن تكون أحرف التحكم مفيدة عند التعامل مع النص. فيما يلي كيفية استبدال حرف التحكم في النص الخاص بك:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // استبدل حرف التحكم "\r" بـ "\r\n".
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

في هذا المثال، نستبدل حرف الإرجاع (`\r`) مع حرف إرجاع متبوعًا بتغذية السطر (`\r\n`).

## خاتمة

تلعب خصائص المستند دورًا مهمًا في إدارة وتنظيم مستنداتك بشكل فعال في Aspose.Words for Java. سواء كنت تعمل مع الخصائص المضمنة، أو الخصائص المخصصة، أو تستخدم أحرف التحكم، فلديك مجموعة من الأدوات تحت تصرفك لتحسين قدرات إدارة المستندات لديك.

## الأسئلة الشائعة

### كيف يمكنني الوصول إلى خصائص المستند المضمنة؟

 للوصول إلى خصائص المستند المضمنة في Aspose.Words for Java، يمكنك استخدام`getBuiltInDocumentProperties` الطريقة على`Document` هدف. تقوم هذه الطريقة بإرجاع مجموعة من الخصائص المضمنة التي يمكنك التكرار من خلالها.

### هل يمكنني إضافة خصائص مستند مخصصة إلى مستند؟

 نعم، يمكنك إضافة خصائص مستند مخصصة إلى مستند باستخدام`CustomDocumentProperties` مجموعة. يمكنك تحديد خصائص مخصصة باستخدام أنواع بيانات مختلفة، بما في ذلك السلاسل والقيم المنطقية والتواريخ والقيم الرقمية.

### كيف يمكنني إزالة خاصية مستند مخصصة معينة؟

 لإزالة خاصية مستند مخصصة معينة، يمكنك استخدام`remove` الطريقة على`CustomDocumentProperties`مجموعة، وتمرير اسم الخاصية التي تريد إزالتها كمعلمة.

### ما هو الغرض من الارتباط بالمحتوى داخل المستند؟

يتيح لك الارتباط بالمحتوى داخل المستند إنشاء مراجع ديناميكية لأجزاء معينة من المستند. يمكن أن يكون هذا مفيدًا لإنشاء مستندات تفاعلية أو إسناد تبادلي بين الأقسام.

### كيف يمكنني التحويل بين وحدات القياس المختلفة في Aspose.Words لـ Java؟

 يمكنك التحويل بين وحدات القياس المختلفة في Aspose.Words for Java باستخدام`ConvertUtil` فصل. فهو يوفر طرقًا لتحويل الوحدات مثل البوصات إلى نقاط، والنقاط إلى سنتيمترات، والمزيد.