---
title: حفظ المستندات كـ Markdown في Aspose.Words لـ Java
linktitle: حفظ المستندات كتخفيض
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية تحويل مستندات Word إلى Markdown باستخدام Aspose.Words لـ Java. يغطي هذا الدليل خطوة بخطوة محاذاة الجدول ومعالجة الصور والمزيد.
type: docs
weight: 18
url: /ar/java/document-loading-and-saving/saving-documents-as-markdown/
---

## مقدمة لحفظ المستندات كـ Markdown في Aspose.Words لـ Java

في هذا الدليل التفصيلي، سنوضح كيفية حفظ المستندات كـ Markdown باستخدام Aspose.Words for Java. Markdown هي لغة ترميزية خفيفة الوزن تُستخدم بشكل شائع لتنسيق المستندات النصية. باستخدام Aspose.Words for Java، يمكنك بسهولة تحويل مستندات Word الخاصة بك إلى تنسيق Markdown. سنغطي الجوانب المختلفة لحفظ ملفات Markdown، بما في ذلك محاذاة محتوى الجدول والتعامل مع الصور.

## المتطلبات الأساسية

قبل البدء، تأكد من توفر المتطلبات الأساسية التالية:

- تم تثبيت Java Development Kit (JDK) على نظامك.
-  Aspose.Words لمكتبة جافا. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).

## الخطوة 1: إنشاء مستند Word

لنبدأ بإنشاء مستند Word الذي سنقوم بتحويله لاحقًا إلى تنسيق Markdown. يمكنك تخصيص هذا المستند وفقًا لمتطلباتك.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إدراج جدول يحتوي على خليتين
builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
builder.write("Cell1");

builder.insertCell();
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.write("Cell2");

// احفظ المستند باسم Markdown
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
doc.save("output.md", saveOptions);
```

 في هذا المثال، قمنا بإنشاء جدول بسيط مكون من خليتين وقمنا بتعيين محاذاة الفقرات داخل هذه الخلايا. ثم نقوم بحفظ المستند باسم Markdown باستخدام ملف`MarkdownSaveOptions`.

## الخطوة 2: تخصيص محاذاة محتوى الجدول

يتيح لك Aspose.Words for Java تخصيص محاذاة محتوى الجدول عند الحفظ كـ Markdown. يمكنك محاذاة محتوى الجدول إلى اليسار، أو اليمين، أو الوسط، أو السماح بتحديده تلقائيًا بناءً على الفقرة الأولى في كل عمود في الجدول.

فيما يلي كيفية تخصيص محاذاة محتوى الجدول:

```java
// قم بتعيين محاذاة محتوى الجدول إلى اليسار
saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
doc.save("left_alignment.md", saveOptions);

// قم بتعيين محاذاة محتوى الجدول إلى اليمين
saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
doc.save("right_alignment.md", saveOptions);

// قم بتعيين محاذاة محتوى الجدول إلى المركز
saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
doc.save("center_alignment.md", saveOptions);

//اضبط محاذاة محتوى الجدول على الوضع التلقائي (يتم تحديده بواسطة الفقرة الأولى)
saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
doc.save("auto_alignment.md", saveOptions);
```

 عن طريق تغيير`TableContentAlignment` الخاصية، يمكنك التحكم في كيفية محاذاة المحتوى داخل الجداول عند التحويل إلى Markdown.

## الخطوة 3: التعامل مع الصور

 لتضمين الصور في مستند Markdown الخاص بك، يجب عليك تحديد المجلد الذي توجد به الصور. يسمح لك Aspose.Words for Java بتعيين مجلد الصور في ملف`MarkdownSaveOptions`.

فيما يلي كيفية تعيين مجلد الصور وحفظ المستند بالصور:

```java
// قم بتحميل مستند يحتوي على صور
Document doc = new Document("document_with_images.docx");

// قم بتعيين مسار مجلد الصور
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
saveOptions.setImagesFolder("images_folder/");

// احفظ المستند بالصور
doc.save("document_with_images.md", saveOptions);
```

 تأكد من استبدال`"document_with_images.docx"` مع المسار إلى مستند Word الخاص بك الذي يحتوي على صور و`"images_folder/"` بالمسار الفعلي إلى المجلد الذي تم تخزين صورك فيه.

## أكمل كود المصدر لحفظ المستندات كتخفيض في Aspose.Words لـ Java

```java
public void autoTableContentAlignment() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
	builder.write("Cell1");
	builder.insertCell();
	builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
	builder.write("Cell2");
	// جعل جميع الفقرات الموجودة داخل الجدول تتم محاذاتها.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions();
	{
		saveOptions.setTableContentAlignment(TableContentAlignment.LEFT);
	}
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.RIGHT);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);
	saveOptions.setTableContentAlignment(TableContentAlignment.CENTER);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);
	// سيتم أخذ المحاذاة في هذه الحالة من الفقرة الأولى في عمود الجدول المقابل.
	saveOptions.setTableContentAlignment(TableContentAlignment.AUTO);
	doc.save("Your Directory Path" + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
}
@Test
public void setImagesFolder() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Image bullet points.docx");
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions(); { saveOptions.setImagesFolder("Your Directory Path" + "Images"); }
	try(ByteArrayOutputStream stream = new ByteArrayOutputStream())
	{
		doc.save(stream, saveOptions);
	}
}
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية حفظ المستندات بتنسيق Markdown باستخدام Aspose.Words لـ Java. لقد قمنا بتغطية إنشاء مستند Word، وتخصيص محاذاة محتوى الجدول، والتعامل مع الصور في ملفات Markdown. يمكنك الآن تحويل مستندات Word بكفاءة إلى تنسيق Markdown، مما يجعلها مناسبة لمختلف منصات النشر واحتياجات التوثيق.

## الأسئلة الشائعة

### كيف أقوم بتثبيت Aspose.Words لـ Java؟

 يمكن تثبيت Aspose.Words for Java عن طريق تضمين المكتبة في مشروع Java الخاص بك. يمكنك تحميل المكتبة من[هنا](https://releases.aspose.com/words/java/) واتبع تعليمات التثبيت المتوفرة في الوثائق.

### هل يمكنني تحويل مستندات Word المعقدة التي تحتوي على جداول وصور إلى Markdown؟

نعم، يدعم Aspose.Words for Java تحويل مستندات Word المعقدة التي تحتوي على جداول وصور وعناصر تنسيق متنوعة إلى Markdown. يمكنك تخصيص مخرجات Markdown وفقًا لتعقيد المستند الخاص بك.

### كيف يمكنني التعامل مع الصور في ملفات Markdown؟

 لتضمين الصور في ملفات Markdown، قم بتعيين مسار مجلد الصور باستخدام ملف`setImagesFolder`طريقة في`MarkdownSaveOptions`. تأكد من تخزين ملفات الصور في المجلد المحدد، وسيتعامل Aspose.Words for Java مع مراجع الصور وفقًا لذلك.

### هل تتوفر نسخة تجريبية من Aspose.Words لـ Java؟

نعم، يمكنك الحصول على نسخة تجريبية من Aspose.Words for Java من موقع Aspose. تتيح لك النسخة التجريبية تقييم إمكانيات المكتبة قبل شراء الترخيص.

### أين يمكنني العثور على المزيد من الأمثلة والوثائق؟

 لمزيد من الأمثلة والوثائق والمعلومات التفصيلية حول Aspose.Words for Java، يرجى زيارة الموقع[توثيق](https://reference.aspose.com/words/java/).