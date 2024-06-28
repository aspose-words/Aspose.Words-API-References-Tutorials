---
title: تحميل الملفات النصية باستخدام Aspose.Words لـ Java
linktitle: تحميل الملفات النصية مع
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: أطلق العنان لقوة Aspose.Words لـ Java. تعلم كيفية تحميل المستندات النصية وإدارة القوائم والتعامل مع المسافات والتحكم في اتجاه النص.
type: docs
weight: 13
url: /ar/java/document-loading-and-saving/loading-text-files/
---

## مقدمة لتحميل الملفات النصية باستخدام Aspose.Words لـ Java

في هذا الدليل، سنستكشف كيفية تحميل الملفات النصية باستخدام Aspose.Words for Java ومعالجتها كمستندات Word. سنغطي جوانب مختلفة مثل اكتشاف القوائم والتعامل مع المساحات والتحكم في اتجاه النص.

## الخطوة 1: الكشف عن القوائم

لتحميل مستند نصي واكتشاف القوائم، يمكنك اتباع الخطوات التالية:

```java
// قم بإنشاء مستند نص عادي على شكل سلسلة تحتوي على أجزاء يمكن تفسيرها على أنها قوائم.
// عند التحميل، سيتم دائمًا اكتشاف القوائم الثلاث الأولى بواسطة Aspose.Words،
// وسيتم إنشاء كائنات القائمة لهم بعد التحميل.
final String TEXT_DOC = "Full stop delimiters:\n" +
        "1. First list item 1\n" +
        "2. First list item 2\n" +
        "3. First list item 3\n\n" +
        "Right bracket delimiters:\n" +
        "1) Second list item 1\n" +
        "2) Second list item 2\n" +
        "3) Second list item 3\n\n" +
        "Bullet delimiters:\n" +
        "• Third list item 1\n" +
        "• Third list item 2\n" +
        "• Third list item 3\n\n" +
        "Whitespace delimiters:\n" +
        "1 Fourth list item 1\n" +
        "2 Fourth list item 2\n" +
        "3 Fourth list item 3";
//القائمة الرابعة، مع وجود مسافة بيضاء بين رقم القائمة ومحتويات عناصر القائمة،
// سيتم اكتشافه كقائمة فقط إذا تم تعيين "DetectNumberingWithWhitespaces" في كائن LoadOptions على القيمة true،
// لتجنب اكتشاف الفقرات التي تبدأ بأرقام كقوائم عن طريق الخطأ.
TxtLoadOptions loadOptions = new TxtLoadOptions();
{
    loadOptions.setDetectNumberingWithWhitespaces(true);
}
// قم بتحميل المستند أثناء تطبيق LoadOptions كمعلمة وتحقق من النتيجة.
Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

 يوضح هذا الرمز كيفية تحميل مستند نصي بتنسيقات قوائم مختلفة واستخدام الملف`DetectNumberingWithWhitespaces` خيار للكشف عن القوائم بشكل صحيح.

## الخطوة 2: التعامل مع خيارات المساحات

للتحكم في المسافات البادئة واللاحقة عند تحميل مستند نصي، يمكنك استخدام الكود التالي:

```java
@Test
public void handleSpacesOptions() throws Exception {
    final String TEXT_DOC = "      Line 1 \n" +
            "    Line 2   \n" +
            " Line 3       ";
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
        loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
    }
    Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
```

 في هذا المثال، نقوم بتحميل مستند نصي وقص المسافات البادئة واللاحقة باستخدام`TxtLeadingSpacesOptions.TRIM` و`TxtTrailingSpacesOptions.TRIM`.

## الخطوة 3: التحكم في اتجاه النص

لتحديد اتجاه النص عند تحميل مستند نصي، يمكنك استخدام الكود التالي:

```java
@Test
public void documentTextDirection() throws Exception {
    TxtLoadOptions loadOptions = new TxtLoadOptions();
    {
        loadOptions.setDocumentDirection(DocumentDirection.AUTO);
    }
    Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
    Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
    System.out.println(paragraph.getParagraphFormat().getBidi());
    doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
}
```

يضبط هذا الرمز اتجاه المستند على الاكتشاف التلقائي (`DocumentDirection.AUTO`ويقوم بتحميل مستند نصي يحتوي على نص عبري. يمكنك ضبط اتجاه المستند حسب الحاجة.

## كود المصدر الكامل لتحميل الملفات النصية باستخدام Aspose.Words لـ Java

```java
public void detectNumberingWithWhitespaces() throws Exception {
	// قم بإنشاء مستند نص عادي على شكل سلسلة تحتوي على أجزاء يمكن تفسيرها على أنها قوائم.
	// عند التحميل، سيتم دائمًا اكتشاف القوائم الثلاث الأولى بواسطة Aspose.Words،
	// وسيتم إنشاء كائنات القائمة لهم بعد التحميل.
	final String TEXT_DOC = "Full stop delimiters:\n" +
			"1. First list item 1\n" +
			"2. First list item 2\n" +
			"3. First list item 3\n\n" +
			"Right bracket delimiters:\n" +
			"1) Second list item 1\n" +
			"2) Second list item 2\n" +
			"3) Second list item 3\n\n" +
			"Bullet delimiters:\n" +
			"• Third list item 1\n" +
			"• Third list item 2\n" +
			"• Third list item 3\n\n" +
			"Whitespace delimiters:\n" +
			"1 Fourth list item 1\n" +
			"2 Fourth list item 2\n" +
			"3 Fourth list item 3";
	// القائمة الرابعة، مع وجود مسافة بيضاء بين رقم القائمة ومحتويات عنصر القائمة،
	// سيتم اكتشافه كقائمة فقط إذا تم تعيين "DetectNumberingWithWhitespaces" في كائن LoadOptions على القيمة true،
	// لتجنب اكتشاف الفقرات التي تبدأ بأرقام كقوائم عن طريق الخطأ.
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDetectNumberingWithWhitespaces(true);
	}
	// قم بتحميل المستند أثناء تطبيق LoadOptions كمعلمة وتحقق من النتيجة.
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
}
@Test
public void handleSpacesOptions() throws Exception {
	final String TEXT_DOC = "      Line 1 \n" +
			"    Line 2   \n" +
			" Line 3       ";
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setLeadingSpacesOptions(TxtLeadingSpacesOptions.TRIM);
		loadOptions.setTrailingSpacesOptions(TxtTrailingSpacesOptions.TRIM);
	}
	Document doc = new Document(new ByteArrayInputStream(TEXT_DOC.getBytes()), loadOptions);
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
}
@Test
public void documentTextDirection() throws Exception {
	TxtLoadOptions loadOptions = new TxtLoadOptions();
	{
		loadOptions.setDocumentDirection(DocumentDirection.AUTO);
	}
	Document doc = new Document("Your Directory Path" + "Hebrew text.txt", loadOptions);
	Paragraph paragraph = doc.getFirstSection().getBody().getFirstParagraph();
	System.out.println(paragraph.getParagraphFormat().getBidi());
	doc.save("Your Directory Path" + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
	}
```

## خاتمة

في هذا الدليل، اكتشفنا كيفية تحميل الملفات النصية باستخدام Aspose.Words لـ Java، واكتشاف القوائم، والتعامل مع المسافات، والتحكم في اتجاه النص. تسمح لك هذه التقنيات بمعالجة المستندات النصية بشكل فعال في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### ما هو Aspose.Words لجافا؟

Aspose.Words for Java هي مكتبة قوية لمعالجة المستندات تتيح للمطورين إنشاء مستندات Word ومعالجتها وتحويلها برمجيًا في تطبيقات Java. فهو يوفر نطاقًا واسعًا من الميزات للعمل مع النصوص والجداول والصور وعناصر المستند الأخرى.

### كيف يمكنني البدء باستخدام Aspose.Words لـ Java؟

لبدء استخدام Aspose.Words لـ Java، اتبع الخطوات التالية:
1. قم بتنزيل وتثبيت مكتبة Aspose.Words لـ Java.
2.  الرجوع إلى الوثائق في[Aspose.Words لمرجع Java API](https://reference.aspose.com/words/java/)للحصول على معلومات وأمثلة مفصلة.
3. استكشف نموذج التعليمات البرمجية والبرامج التعليمية لمعرفة كيفية استخدام المكتبة بفعالية.

### كيف أقوم بتحميل مستند نصي باستخدام Aspose.Words لـ Java؟

 لتحميل مستند نصي باستخدام Aspose.Words for Java، يمكنك استخدام الملف`TxtLoadOptions` الطبقة و`Document` فصل. تأكد من تحديد الخيارات المناسبة للتعامل مع المسافات واتجاه النص حسب الحاجة. ارجع إلى الدليل التفصيلي الموجود في هذه المقالة للحصول على مثال تفصيلي.

### هل يمكنني تحويل مستند نصي محمل إلى تنسيقات أخرى؟

 نعم، يسمح لك Aspose.Words for Java بتحويل مستند نصي محمل إلى تنسيقات مختلفة، بما في ذلك DOCX وPDF والمزيد. يمكنك استخدام ال`Document` فئة لإجراء التحويلات. تحقق من الوثائق للحصول على أمثلة تحويل محددة.

### كيف أتعامل مع المسافات في المستندات النصية المحملة؟

 يمكنك التحكم في كيفية التعامل مع المسافات البادئة والزائدة في المستندات النصية المحملة باستخدام`TxtLoadOptions` . خيارات مثل`TxtLeadingSpacesOptions` و`TxtTrailingSpacesOptions`تسمح لك بقص المساحات أو الحفاظ عليها حسب الحاجة. راجع قسم "خيارات التعامل مع المساحات" في هذا الدليل للحصول على مثال.

### ما أهمية اتجاه النص في Aspose.Words لـ Java؟

يعد اتجاه النص ضروريًا للمستندات التي تحتوي على نصوص أو لغات مختلطة، مثل العبرية أو العربية. يوفر Aspose.Words for Java خيارات لتحديد اتجاه النص، مما يضمن العرض والتنسيق المناسبين للنص بهذه اللغات. يوضح قسم "التحكم في اتجاه النص" في هذا الدليل كيفية ضبط اتجاه النص.

### أين يمكنني العثور على المزيد من الموارد والدعم لـ Aspose.Words لـ Java؟

 للحصول على موارد إضافية، والوثائق، والدعم، قم بزيارة[Aspose.Words لتوثيق جافا](https://reference.aspose.com/words/java/). يمكنك أيضًا المشاركة في منتديات مجتمع Aspose.Words أو الاتصال بدعم Aspose للحصول على المساعدة بشأن مشكلات أو استفسارات محددة.

### هل Aspose.Words for Java مناسب للمشاريع التجارية؟

نعم، Aspose.Words for Java مناسب لكل من المشاريع الشخصية والتجارية. ويقدم خيارات الترخيص لاستيعاب سيناريوهات الاستخدام المختلفة. تأكد من مراجعة شروط الترخيص والأسعار على موقع Aspose لاختيار الترخيص المناسب لمشروعك.