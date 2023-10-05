---
title: إضافة محتوى باستخدام DocumentBuilder في Aspose.Words لـ Java
linktitle: إضافة محتوى باستخدام DocumentBuilder
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: إنشاء المستندات بشكل رئيسي باستخدام Aspose.Words لـ Java. دليل خطوة بخطوة لإضافة نص وجداول وصور والمزيد. قم بإنشاء مستندات Word مذهلة دون عناء.
type: docs
weight: 26
url: /ar/java/document-manipulation/adding-content-using-documentbuilder/
---

## مقدمة لإضافة محتوى باستخدام DocumentBuilder في Aspose.Words لـ Java

في هذا الدليل التفصيلي، سنستكشف كيفية استخدام Aspose.Words for DocumentBuilder الخاص بـ Java لإضافة أنواع مختلفة من المحتوى إلى مستند Word. سنغطي إدراج النص والجداول والقواعد الأفقية وحقول النموذج وHTML والارتباطات التشعبية وجدول المحتويات والصور المضمنة والعائمة والفقرات والمزيد. هيا بنا نبدأ!

## المتطلبات الأساسية

 قبل أن تبدأ، تأكد من إعداد مكتبة Aspose.Words for Java في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).

## إضافة نص

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل فقرة نصية بسيطة
builder.write("This is a simple text paragraph.");

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة الجداول

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ابدأ الجدول
Table table = builder.startTable();

// إدراج الخلايا والمحتوى
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// قم بإنهاء الجدول
builder.endTable();

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة القاعدة الأفقية

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل قاعدة أفقية
builder.insertHorizontalRule();

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة حقول النموذج

### حقل نموذج إدخال النص

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل حقل نموذج إدخال النص
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// احفظ المستند
doc.save("path/to/your/document.docx");
```

### حقل نموذج خانة الاختيار

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإدراج حقل نموذج خانة الاختيار
builder.insertCheckBox("CheckBox", true, true, 0);

// احفظ المستند
doc.save("path/to/your/document.docx");
```

### حقل نموذج مربع التحرير والسرد

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تحديد العناصر لمربع التحرير والسرد
String[] items = { "Option 1", "Option 2", "Option 3" };

// قم بإدراج حقل نموذج مربع التحرير والسرد
builder.insertComboBox("DropDown", items, 0);

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة HTML

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل محتوى HTML
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة الارتباطات التشعبية

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بإدراج ارتباط تشعبي
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com"، خطأ)؛
builder.getFont().clearFormatting();
builder.write(" for more information.");

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة جدول المحتويات

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل جدول المحتويات
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// إضافة محتوى المستند
// ...

// تحديث جدول المحتويات
doc.updateFields();

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة الصور

### صورة مضمنة

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج صورة مضمنة
builder.insertImage("path/to/your/image.png");

// احفظ المستند
doc.save("path/to/your/document.docx");
```

### الصورة العائمة

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل صورة عائمة
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## إضافة الفقرات

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ضبط تنسيق الفقرة
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// أدخل فقرة
builder.writeln("This is a formatted paragraph.");

// احفظ المستند
doc.save("path/to/your/document.docx");
```

## الخطوة 10: تحريك المؤشر

 يمكنك التحكم في موضع المؤشر داخل المستند باستخدام طرق مختلفة مثل`moveToParagraph`, `moveToCell`، و اكثر. هنا مثال:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// نقل المؤشر إلى فقرة معينة
builder.moveToParagraph(2, 0);

// أضف محتوى في موضع المؤشر الجديد
builder.writeln("This is the 3rd paragraph.");
```

هذه بعض العمليات الشائعة التي يمكنك تنفيذها باستخدام Aspose.Words لـ DocumentBuilder الخاص بـ Java. استكشف وثائق المكتبة للحصول على المزيد من الميزات المتقدمة وخيارات التخصيص. إنشاء مستند سعيد!


## خاتمة

في هذا الدليل الشامل، اكتشفنا إمكانيات Aspose.Words لبرنامج DocumentBuilder الخاص بـ Java لإضافة أنواع مختلفة من المحتوى إلى مستندات Word. لقد قمنا بتغطية النص والجداول والقواعد الأفقية وحقول النموذج وHTML والارتباطات التشعبية وجدول المحتويات والصور والفقرات وحركة المؤشر.

## الأسئلة الشائعة

### س: ما هو Aspose.Words لـ Java؟

ج: Aspose.Words for Java هي مكتبة Java تسمح للمطورين بإنشاء مستندات Microsoft Word وتعديلها ومعالجتها برمجيًا. فهو يوفر مجموعة واسعة من الميزات لإنشاء المستندات وتنسيقها وإدراج المحتوى.

### س: كيف يمكنني إضافة جدول محتويات إلى مستندي؟

ج: لإضافة جدول محتويات، استخدم`DocumentBuilder` لإدراج حقل جدول المحتويات في المستند الخاص بك. تأكد من تحديث الحقول الموجودة في المستند بعد إضافة المحتوى لملء جدول المحتويات. هنا مثال:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل حقل جدول المحتويات
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// إضافة محتوى المستند
// ...

// تحديث جدول المحتويات
doc.updateFields();
```

### س: كيف يمكنني إدراج صور في مستند باستخدام Aspose.Words for Java؟

 ج: يمكنك إدراج الصور، سواء المضمنة أو العائمة، باستخدام`DocumentBuilder`. فيما يلي أمثلة على كليهما:

#### الصورة المضمنة:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج صورة مضمنة
builder.insertImage("path/to/your/image.png");
```

#### الصورة العائمة:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل صورة عائمة
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### س: هل يمكنني تنسيق النص والفقرات عند إضافة محتوى؟

 ج: نعم، يمكنك تنسيق النص والفقرات باستخدام`DocumentBuilder`. يمكنك تعيين خصائص الخط ومحاذاة الفقرة والمسافة البادئة والمزيد. هنا مثال:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ضبط تنسيق الخط والفقرة
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// إدراج فقرة منسقة
builder.writeln("This is a formatted paragraph.");
```

### س: كيف يمكنني تحريك المؤشر إلى موقع محدد داخل المستند؟

 ج: يمكنك التحكم في موضع المؤشر باستخدام طرق مثل`moveToParagraph`, `moveToCell`، و اكثر. هنا مثال:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// نقل المؤشر إلى فقرة معينة
builder.moveToParagraph(2, 0);

// أضف محتوى في موضع المؤشر الجديد
builder.writeln("This is the 3rd paragraph.");
```

هذه بعض الأسئلة والإجابات الشائعة لمساعدتك على بدء استخدام Aspose.Words for DocumentBuilder الخاص بـ Java. إذا كان لديك المزيد من الأسئلة أو كنت بحاجة إلى مزيد من المساعدة، فارجع إلى[توثيق المكتبة](https://reference.aspose.com/words/java/) أو اطلب المساعدة من مجتمع Aspose.Words وموارد الدعم.