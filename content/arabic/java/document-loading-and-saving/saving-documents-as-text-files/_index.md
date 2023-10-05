---
title: حفظ المستندات كملفات نصية في Aspose.Words لـ Java
linktitle: حفظ المستندات كملفات نصية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية حفظ المستندات كملفات نصية في Aspose.Words لـ Java. اتبع دليلنا خطوة بخطوة مع أمثلة كود Java.
type: docs
weight: 24
url: /ar/java/document-loading-and-saving/saving-documents-as-text-files/
---

## مقدمة لحفظ المستندات كملفات نصية في Aspose.Words لـ Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية حفظ المستندات كملفات نصية باستخدام مكتبة Aspose.Words for Java. Aspose.Words عبارة عن واجهة برمجة تطبيقات Java قوية للعمل مع مستندات Word، وتوفر خيارات متنوعة لحفظ المستندات بتنسيقات مختلفة، بما في ذلك النص العادي. سنغطي الخطوات اللازمة لتحقيق ذلك ونقدم نموذجًا لتعليمات Java البرمجية على طول الطريق.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Words لمكتبة Java المدمجة في مشروعك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).
- المعرفة الأساسية ببرمجة جافا.

## الخطوة 1: إنشاء مستند

لحفظ مستند كملف نصي، نحتاج أولاً إلى إنشاء مستند باستخدام Aspose.Words. فيما يلي مقتطف بسيط من كود Java لإنشاء مستند يحتوي على بعض المحتوى:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

في هذا الكود، نقوم بإنشاء مستند جديد وإضافة بعض النص إليه، بما في ذلك النص بلغات مختلفة.

## الخطوة 2: تحديد خيارات حفظ النص

بعد ذلك، نحتاج إلى تحديد خيارات حفظ النص التي تحدد كيفية حفظ المستند كملف نصي. يمكننا تكوين إعدادات مختلفة مثل إضافة علامات ثنائية الاتجاه والمسافات البادئة للقائمة والمزيد. دعونا ننظر إلى مثالين:

### مثال 1: إضافة علامات بيدي

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 في هذا المثال، نقوم بإنشاء`TxtSaveOptions` الكائن وتعيين`AddBidiMarks`الملكية ل`true` لتضمين علامات ثنائية في إخراج النص.

### المثال 2: استخدام حرف الجدولة للمسافة البادئة للقائمة

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

هنا، نقوم بتكوين خيارات الحفظ لاستخدام حرف علامة التبويب للمسافة البادئة للقائمة مع عدد 1.

## الخطوة 3: احفظ المستند كنص

الآن بعد أن حددنا خيارات حفظ النص، يمكننا حفظ المستند كملف نصي. يوضح التعليمة البرمجية التالية كيفية القيام بذلك:

```java
doc.save("output.txt", saveOptions);
```

 يستبدل`"output.txt"` باستخدام مسار الملف المطلوب حيث تريد حفظ الملف النصي.

## أكمل كود المصدر لحفظ المستندات كملفات نصية في Aspose.Words لـ Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // قم بإنشاء قائمة بثلاثة مستويات من المسافة البادئة.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // قم بإنشاء قائمة بثلاثة مستويات من المسافة البادئة.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## خاتمة

في هذا البرنامج التعليمي، تعلمنا كيفية حفظ المستندات كملفات نصية في Aspose.Words لـ Java. لقد تناولنا خطوات إنشاء مستند وتحديد خيارات حفظ النص وحفظ المستند بتنسيق نص. يوفر Aspose.Words مرونة واسعة النطاق عندما يتعلق الأمر بحفظ المستندات، مما يسمح لك بتخصيص المخرجات وفقًا لمتطلباتك المحددة.

## الأسئلة الشائعة

### كيف أقوم بإضافة علامات بيدي إلى إخراج النص؟

 لإضافة علامات ثنائية الاتجاه إلى مخرجات النص، قم بتعيين`AddBidiMarks` ممتلكات`TxtSaveOptions` ل`true`. على سبيل المثال:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### هل يمكنني تخصيص حرف المسافة البادئة للقائمة؟

 نعم، يمكنك تخصيص حرف المسافة البادئة للقائمة عن طريق تكوين`ListIndentation` ممتلكات`TxtSaveOptions`. على سبيل المثال، لاستخدام حرف جدولة للمسافة البادئة للقائمة، يمكنك القيام بما يلي:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### هل Aspose.Words for Java مناسب للتعامل مع النص متعدد اللغات؟

نعم، Aspose.Words for Java مناسب للتعامل مع النص متعدد اللغات. وهو يدعم العديد من اللغات وترميزات الأحرف، مما يجعله خيارًا متعدد الاستخدامات للعمل مع المستندات بلغات مختلفة.

### كيف يمكنني الوصول إلى المزيد من الوثائق والموارد الخاصة بـ Aspose.Words لـ Java؟

 يمكنك العثور على وثائق وموارد شاملة لـ Aspose.Words for Java على موقع وثائق Aspose:[Aspose.Words لتوثيق جافا](https://reference.aspose.com/words/java/).

### أين يمكنني تنزيل Aspose.Words لـ Java؟

 يمكنك تنزيل مكتبة Aspose.Words for Java من موقع Aspose الإلكتروني:[تحميل Aspose.Words لجافا](https://releases.aspose.com/words/java/).