---
title: استخدام خيارات التحميل في Aspose.Words لـ Java
linktitle: استخدام خيارات التحميل
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: إتقان خيارات التحميل في Aspose.Words لـ Java. قم بتخصيص تحميل المستندات والتعامل مع التشفير وتحويل الأشكال وتعيين إصدارات Word والمزيد لمعالجة مستندات Java بكفاءة.
type: docs
weight: 11
url: /ar/java/document-loading-and-saving/using-load-options/
---

## مقدمة للعمل مع خيارات التحميل في Aspose.Words لـ Java

في هذا البرنامج التعليمي، سوف نستكشف كيفية العمل مع خيارات التحميل في Aspose.Words لـ Java. تتيح لك خيارات التحميل تخصيص كيفية تحميل المستندات ومعالجتها. سنغطي سيناريوهات مختلفة، بما في ذلك تحديث الحقول المتسخة، وتحميل المستندات المشفرة، وتحويل الأشكال إلى Office Math، وتعيين إصدار MS Word، وتحديد مجلد مؤقت، ومعالجة التحذيرات، وتحويل ملفات التعريف إلى PNG. دعونا نتعمق خطوة بخطوة.

## تحديث الحقول القذرة

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setUpdateDirtyFields(true);

Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
```

 يوضح مقتطف التعليمات البرمجية هذا كيفية تحديث الحقول المتسخة في المستند. ال`setUpdateDirtyFields(true)` يتم استخدام الطريقة للتأكد من تحديث الحقول المتسخة أثناء تحميل المستند.

## تحميل مستند مشفر

```java
@Test
public void loadEncryptedDocument() throws Exception {
    Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
```

 هنا، نقوم بتحميل مستند مشفر باستخدام كلمة مرور. ال`LoadOptions` يقبل المُنشئ كلمة مرور المستند، ويمكنك أيضًا تحديد كلمة مرور جديدة عند حفظ المستند باستخدام`OdtSaveOptions`.

## تحويل الشكل إلى مكتب الرياضيات

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setConvertShapeToOfficeMath(true);

Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
```

 يوضح هذا الرمز كيفية تحويل الأشكال إلى كائنات Office Math أثناء تحميل المستند. ال`setConvertShapeToOfficeMath(true)`طريقة تمكن هذا التحويل.

## تعيين إصدار MS Word

```java
@Test
public void setMsWordVersion() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setMswVersion(MsWordVersion.WORD_2010);

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
    doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
```

 يمكنك تحديد إصدار MS Word لتحميل المستندات. في هذا المثال، قمنا بتعيين الإصدار إلى Microsoft Word 2010 باستخدام`setMswVersion`.

## استخدم المجلد المؤقت

```java
@Test
public void useTempFolder() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setTempFolder("Your Directory Path");

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
```

 عن طريق تعيين المجلد المؤقت باستخدام`setTempFolder`، يمكنك التحكم في مكان تخزين الملفات المؤقتة أثناء معالجة المستندات.

## رد تحذير

```java
@Test
public void warningCallback() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());

    Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}

public static class DocumentLoadingWarningCallback implements IWarningCallback {
    public void warning(WarningInfo info) {
        // تعامل مع التحذيرات عند ظهورها أثناء تحميل المستندات.
        System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
        System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
    }
}
```

يوضح هذا الرمز كيفية إعداد رد اتصال تحذيري للتعامل مع التحذيرات أثناء تحميل المستند. يمكنك تخصيص سلوك التطبيق الخاص بك عند حدوث تحذيرات.

## تحويل ملفات التعريف إلى PNG

```java
@Test
public void convertMetafilesToPng() throws Exception {
    LoadOptions loadOptions = new LoadOptions();
    loadOptions.setConvertMetafilesToPng(true);

    Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
```

 لتحويل ملفات التعريف (على سبيل المثال، WMF) إلى صور PNG أثناء تحميل المستندات، يمكنك استخدام ملف`setConvertMetafilesToPng(true)` طريقة.

## كود المصدر الكامل للعمل مع خيارات التحميل في Aspose.Words لـ Java

```java
public void updateDirtyFields() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setUpdateDirtyFields(true);
	}
	Document doc = new Document("Your Directory Path" + "Dirty field.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.UpdateDirtyFields.docx");
}
@Test
public void loadEncryptedDocument() throws Exception {
	Document doc = new Document("Your Directory Path" + "Encrypted.docx", new LoadOptions("docPassword"));
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newPassword"));
}
@Test
public void convertShapeToOfficeMath() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertShapeToOfficeMath(true);
	}
	Document doc = new Document("Your Directory Path" + "Office math.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.ConvertShapeToOfficeMath.docx", SaveFormat.DOCX);
}
@Test
public void setMsWordVersion() throws Exception {
	// قم بإنشاء كائن LoadOptions جديد، والذي سيقوم بتحميل المستندات وفقًا لمواصفات MS Word 2019 افتراضيًا
	// وقم بتغيير إصدار التحميل إلى Microsoft Word 2010.
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setMswVersion(MsWordVersion.WORD_2010);
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
	doc.save("Your Directory Path" + "WorkingWithLoadOptions.SetMsWordVersion.docx");
}
@Test
public void useTempFolder() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setTempFolder("Your Directory Path");
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
@Test
public void warningCallback() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setWarningCallback(new DocumentLoadingWarningCallback());
	}
	Document doc = new Document("Your Directory Path" + "Document.docx", loadOptions);
}
public static class DocumentLoadingWarningCallback implements IWarningCallback {
	public void warning(WarningInfo info) {
		//طباعة التحذيرات وتفاصيلها فور ظهورها أثناء تحميل المستندات.
		System.out.println(MessageFormat.format("WARNING: {0}, source: {1}", info.getWarningType(), info.getSource()));
		System.out.println(MessageFormat.format("\tDescription: {0}", info.getDescription()));
	}
}
@Test
public void convertMetafilesToPng() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setConvertMetafilesToPng(true);
	}
	Document doc = new Document("Your Directory Path" + "WMF with image.docx", loadOptions);
}
@Test
public void loadChm() throws Exception {
	LoadOptions loadOptions = new LoadOptions();
	{
		loadOptions.setEncoding(Charset.forName("windows-1251"));
	}
	Document doc = new Document("Your Directory Path" + "HTML help.chm", loadOptions);
}
```

## خاتمة

في هذا البرنامج التعليمي، تناولنا جوانب مختلفة من العمل باستخدام خيارات التحميل في Aspose.Words for Java. تلعب خيارات التحميل دورًا حاسمًا في تخصيص كيفية تحميل المستندات ومعالجتها، مما يسمح لك بتخصيص معالجة المستندات وفقًا لاحتياجاتك المحددة. دعونا نلخص النقاط الرئيسية التي يغطيها هذا الدليل:

## الأسئلة الشائعة

### كيف يمكنني التعامل مع التحذيرات أثناء تحميل المستندات؟

 يمكنك إعداد رد اتصال تحذيري كما هو موضح في`warningCallback()` الطريقة أعلاه. تخصيص`DocumentLoadingWarningCallback` class للتعامل مع التحذيرات وفقًا لمتطلبات التطبيق الخاص بك.

### هل يمكنني تحويل الأشكال إلى كائنات Office Math عند تحميل مستند؟

 نعم، يمكنك تحويل الأشكال إلى كائنات Office Math باستخدام`loadOptions.setConvertShapeToOfficeMath(true)`.

### كيف أحدد إصدار MS Word لتحميل المستندات؟

 يستخدم`loadOptions.setMswVersion(MsWordVersion.WORD_2010)` لتحديد إصدار MS Word لتحميل المستندات.

###  ما هو الغرض من`setTempFolder` method in Load Options?

 ال`setTempFolder`تسمح لك هذه الطريقة بتحديد المجلد الذي يتم فيه تخزين الملفات المؤقتة أثناء معالجة المستندات.