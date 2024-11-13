---
title: حفظ المستندات بصيغة OOXML في Aspose.Words لـ Java
linktitle: حفظ المستندات بصيغة OOXML
second_title: واجهة برمجة تطبيقات معالجة المستندات في Java Aspose.Words
description: تعرف على كيفية حفظ المستندات بتنسيق OOXML باستخدام Aspose.Words for Java. قم بتأمين ملفاتك وتحسينها وتخصيصها بسهولة.
type: docs
weight: 20
url: /ar/java/document-loading-and-saving/saving-documents-as-ooxml-format/
---

## مقدمة لحفظ المستندات بتنسيق OOXML في Aspose.Words لـ Java

في هذا الدليل، سنستكشف كيفية حفظ المستندات بتنسيق OOXML باستخدام Aspose.Words for Java. OOXML (Office Open XML) هو تنسيق ملف يستخدمه Microsoft Word وتطبيقات Office الأخرى. سنغطي خيارات وإعدادات مختلفة لحفظ المستندات بتنسيق OOXML.

## المتطلبات الأساسية

قبل أن نبدأ، تأكد من إعداد مكتبة Aspose.Words for Java في مشروعك.

## حفظ مستند باستخدام تشفير كلمة المرور

يمكنك تشفير مستندك بكلمة مرور أثناء حفظه بتنسيق OOXML. إليك كيفية القيام بذلك:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// تحميل المستند
Document doc = new Document("Document.docx");

// إنشاء OoxmlSaveOptions وتعيين كلمة المرور
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setPassword("password");

// حفظ المستند بالتشفير
doc.save("EncryptedDoc.docx", saveOptions);
```

## إعداد التوافق مع OOXML

يمكنك تحديد مستوى توافق OOXML عند حفظ المستند. على سبيل المثال، يمكنك تعيينه على ISO 29500:2008 (صارم). وإليك الطريقة:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.MsWordVersion;
import com.aspose.words.OoxmlCompliance;

// تحميل المستند
Document doc = new Document("Document.docx");

// تحسين Word 2016
doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);

// إنشاء OoxmlSaveOptions وتعيين مستوى الامتثال
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT);

// حفظ المستند بإعدادات التوافق
doc.save("ComplianceDoc.docx", saveOptions);
```

## تحديث خاصية آخر وقت تم حفظه

يمكنك اختيار تحديث خاصية "آخر وقت تم حفظه" للمستند عند حفظه. وإليك الطريقة:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;

// تحميل المستند
Document doc = new Document("Document.docx");

// إنشاء OoxmlSaveOptions وتمكين تحديث خاصية Last Saved Time
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setUpdateLastSavedTimeProperty(true);

// احفظ المستند بالخاصية المحدثة
doc.save("UpdatedLastSavedTime.docx", saveOptions);
```

## الحفاظ على شخصيات التحكم القديمة

إذا كانت مستندك تحتوي على أحرف تحكم قديمة، فيمكنك اختيار الاحتفاظ بها أثناء الحفظ. وإليك الطريقة:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.SaveFormat;

//تحميل مستند يحتوي على أحرف تحكم قديمة
Document doc = new Document("LegacyControlChars.doc");

// إنشاء OoxmlSaveOptions بتنسيق FLAT_OPC وتمكين الاحتفاظ بأحرف التحكم القديمة
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC);
saveOptions.setKeepLegacyControlChars(true);

// حفظ المستند باستخدام أحرف التحكم القديمة
doc.save("LegacyControlCharsPreserved.docx", saveOptions);
```

## ضبط مستوى الضغط

يمكنك ضبط مستوى الضغط عند حفظ المستند. على سبيل المثال، يمكنك ضبطه على SUPER_FAST للحصول على الحد الأدنى من الضغط. وإليك الطريقة:

```java
import com.aspose.words.Document;
import com.aspose.words.OoxmlSaveOptions;
import com.aspose.words.CompressionLevel;

// تحميل المستند
Document doc = new Document("Document.docx");

// إنشاء OoxmlSaveOptions وتعيين مستوى الضغط
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST);

// احفظ المستند بمستوى الضغط المحدد
doc.save("FastCompressionDoc.docx", saveOptions);
```

هذه بعض الخيارات والإعدادات الرئيسية التي يمكنك استخدامها عند حفظ المستندات بتنسيق OOXML باستخدام Aspose.Words for Java. لا تتردد في استكشاف المزيد من الخيارات وتخصيص عملية حفظ المستندات حسب الحاجة.

## الكود المصدر الكامل لحفظ المستندات بتنسيق OOXML في Aspose.Words لـ Java

```java
public void encryptDocxWithPassword() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setPassword("password"); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
}
@Test
public void ooxmlComplianceIso29500_2008_Strict() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2016);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.OoxmlComplianceIso29500_2008_Strict.docx", saveOptions);
}
@Test
public void updateLastSavedTimeProperty() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setUpdateLastSavedTimeProperty(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
}
@Test
public void keepLegacyControlChars() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Legacy control character.doc");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FLAT_OPC); { saveOptions.setKeepLegacyControlChars(true); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
}
@Test
public void setCompressionLevel() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(); { saveOptions.setCompressionLevel(CompressionLevel.SUPER_FAST); }
	doc.save("Your Directory Path" + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
}
```

## خاتمة

في هذا الدليل الشامل، استكشفنا كيفية حفظ المستندات بتنسيق OOXML باستخدام Aspose.Words for Java. سواء كنت بحاجة إلى تشفير مستنداتك بكلمات مرور، أو ضمان الامتثال لمعايير OOXML المحددة، أو تحديث خصائص المستند، أو الحفاظ على أحرف التحكم القديمة، أو ضبط مستويات الضغط، فإن Aspose.Words يوفر مجموعة متعددة الاستخدامات من الأدوات لتلبية متطلباتك.

## الأسئلة الشائعة

### كيف يمكنني إزالة الحماية بكلمة مرور من مستند محمي بكلمة مرور؟

لإزالة الحماية بكلمة مرور من مستند محمي بكلمة مرور، يمكنك فتح المستند بكلمة المرور الصحيحة ثم حفظه دون تحديد كلمة مرور في خيارات الحفظ. سيؤدي هذا إلى حفظ المستند دون حماية بكلمة مرور.

### هل يمكنني تعيين خصائص مخصصة عند حفظ مستند بتنسيق OOXML؟

 نعم، يمكنك تعيين خصائص مخصصة لمستند قبل حفظه بتنسيق OOXML. استخدم`BuiltInDocumentProperties` و`CustomDocumentProperties` الفئات لتعيين خصائص مختلفة مثل المؤلف والعنوان والكلمات الرئيسية والخصائص المخصصة.

### ما هو مستوى الضغط الافتراضي عند حفظ مستند بتنسيق OOXML؟

 مستوى الضغط الافتراضي عند حفظ مستند بتنسيق OOXML باستخدام Aspose.Words for Java هو`NORMAL` يمكنك تغيير مستوى الضغط إلى`SUPER_FAST` أو`MAXIMUM` حسب الحاجة.