---
title: استخدام الإشارات المرجعية في Aspose.Words لـ Java
linktitle: استخدام الإشارات المرجعية
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: قم بتحسين معالجة المستندات الخاصة بك باستخدام Aspose.Words for Java. تعلم كيفية استخدام الإشارات المرجعية للتنقل والتعامل بكفاءة مع المحتوى في هذا الدليل المفصّل خطوة بخطوة.
type: docs
weight: 17
url: /ar/java/document-manipulation/using-bookmarks/
---

## مقدمة لاستخدام الإشارات المرجعية في Aspose.Words لـ Java

تعد الإشارات المرجعية ميزة قوية في Aspose.Words for Java والتي تتيح لك وضع علامة على أجزاء معينة من المستند ومعالجتها. في هذا الدليل التفصيلي، سنستكشف كيفية استخدام الإشارات المرجعية في Aspose.Words for Java لتحسين معالجة المستندات لديك. 

## الخطوة 1: إنشاء إشارة مرجعية

لإنشاء إشارة مرجعية، اتبع الخطوات التالية:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// ابدأ الإشارة المرجعية
builder.startBookmark("My Bookmark");
builder.writeln("Text inside a bookmark.");

//قم بإنهاء الإشارة المرجعية
builder.endBookmark("My Bookmark");
```

## الخطوة 2: الوصول إلى الإشارات المرجعية

يمكنك الوصول إلى الإشارات المرجعية في المستند باستخدام فهرسها أو اسمها. وإليك الطريقة:

```java
Document doc = new Document("Your Directory Path" + "Bookmarks.docx");

// حسب الفهرس:
Bookmark bookmark1 = doc.getRange().getBookmarks().get(0);

// بالاسم:
Bookmark bookmark2 = doc.getRange().getBookmarks().get("MyBookmark3");
```

## الخطوة 3: تحديث بيانات الإشارة المرجعية

لتحديث بيانات الإشارة المرجعية، استخدم الكود التالي:

```java
Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
Bookmark bookmark = doc.getRange().getBookmarks().get("MyBookmark1");
String name = bookmark.getName();
String text = bookmark.getText();
bookmark.setName("RenamedBookmark");
bookmark.setText("This is new bookmarked text.");
```

## الخطوة 4: العمل مع النص الذي تم وضع إشارة مرجعية عليه

يمكنك نسخ النص الذي تم وضع إشارة مرجعية عليه وإضافته إلى مستند آخر. وإليك الطريقة:

```java
Document srcDoc = new Document("Your Directory Path" + "Bookmarks.docx");
Bookmark srcBookmark = srcDoc.getRange().getBookmarks().get("MyBookmark1");
Document dstDoc = new Document();
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
appendBookmarkedText(importer, srcBookmark, dstDoc.getLastSection().getBody());
dstDoc.save("Your Directory Path" + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## الخطوة 5: إظهار وإخفاء الإشارات المرجعية

يمكنك إظهار أو إخفاء الإشارات المرجعية في المستند. هنا مثال:

```java
Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
showHideBookmarkedContent(doc, "MyBookmark1", false);
doc.save("Your Directory Path" + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

## الخطوة 6: فك تشابك الإشارات المرجعية

يتيح لك فك تشابك الإشارات المرجعية للصف العمل معها بشكل أكثر فعالية:

```java
Document doc = new Document("Your Directory Path" + "Table column bookmarks.docx");
untangle(doc);
deleteRowByBookmark(doc, "ROW2");
doc.save("Your Directory Path" + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

## خاتمة

يمكن أن يؤدي استخدام الإشارات المرجعية في Aspose.Words for Java إلى تبسيط مهام معالجة المستندات بشكل كبير. سواء كنت بحاجة إلى التنقل في المحتوى أو استخراجه أو معالجته، فإن الإشارات المرجعية توفر آلية قوية للقيام بذلك بكفاءة.

## الأسئلة الشائعة

### كيف أقوم بإنشاء إشارة مرجعية في خلية جدول؟

 لإنشاء إشارة مرجعية في خلية جدول، استخدم`DocumentBuilder` فئة وبدء وإنهاء الإشارة المرجعية داخل الخلية.

### هل يمكنني نسخ إشارة مرجعية إلى مستند آخر؟

 نعم، يمكنك نسخ إشارة مرجعية إلى مستند آخر باستخدام`NodeImporter` فئة لضمان الحفاظ على التنسيق.

### كيف يمكنني حذف صف حسب الإشارة المرجعية الخاصة به؟

يمكنك حذف صف حسب الإشارة المرجعية الخاصة به عن طريق البحث أولاً عن الصف الذي تم وضع إشارة مرجعية عليه ثم إزالته من المستند.

### ما هي بعض حالات الاستخدام الشائعة للإشارات المرجعية؟

تُستخدم الإشارات المرجعية بشكل شائع لإنشاء جدول المحتويات واستخراج محتوى محدد وأتمتة عمليات إنشاء المستندات.

### أين يمكنني العثور على مزيد من المعلومات حول Aspose.Words for Java؟

 للحصول على الوثائق التفصيلية والتنزيلات، تفضل بزيارة[Aspose.Words لتوثيق جافا](https://reference.aspose.com/words/java/).