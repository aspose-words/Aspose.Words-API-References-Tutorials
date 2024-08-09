---
title: استنساخ المستندات ودمجها في Aspose.Words لـ Java
linktitle: الاستنساخ والجمع بين الوثائق
second_title: Aspose.Words واجهة برمجة تطبيقات معالجة مستندات جافا
description: تعرف على كيفية استنساخ المستندات ودمجها في Aspose.Words لـ Java. دليل خطوة بخطوة مع أمثلة التعليمات البرمجية المصدر.
type: docs
weight: 27
url: /ar/java/document-manipulation/cloning-and-combining-documents/
---

## مقدمة لاستنساخ المستندات ودمجها في Aspose.Words لـ Java

في هذا البرنامج التعليمي، سنستكشف كيفية استنساخ المستندات ودمجها باستخدام Aspose.Words for Java. سنقوم بتغطية العديد من السيناريوهات، بما في ذلك استنساخ مستند، وإدراج المستندات عند نقاط الاستبدال، والإشارات المرجعية، وأثناء عمليات دمج البريد.

## الخطوة 1: استنساخ مستند

 لاستنساخ مستند في Aspose.Words لـ Java، يمكنك استخدام`deepClone()` طريقة. إليك مثال بسيط:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "CloneAndCombineDocuments.CloningDocument.docx");
```

سيؤدي هذا الرمز إلى إنشاء نسخة عميقة من المستند الأصلي وحفظه كملف جديد.

## الخطوة 2: إدراج المستندات في نقاط الاستبدال

يمكنك إدراج المستندات عند نقاط استبدال محددة في مستند آخر. وإليك كيف يمكنك القيام بذلك:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

 في هذا المثال نستخدم أ`FindReplaceOptions` كائن لتحديد معالج رد الاتصال للاستبدال. ال`InsertDocumentAtReplaceHandler` يتعامل الفصل مع منطق الإدراج.

## الخطوة 3: إدراج المستندات في الإشارات المرجعية

لإدراج مستند عند إشارة مرجعية معينة في مستند آخر، يمكنك استخدام الكود التالي:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
Document subDoc = new Document("Your Directory Path" + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

 هنا نجد الإشارة المرجعية بالاسم ونستخدمها`insertDocument` طريقة إدراج محتوى`subDoc` المستند في موقع الإشارة المرجعية.

## الخطوة 4: إدراج المستندات أثناء دمج المراسلات

يمكنك إدراج المستندات أثناء عملية دمج البريد في Aspose.Words for Java. وإليك الطريقة:

```java
Document mainDoc = new Document("Your Directory Path" + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { "Your Directory Path" + "Document insertion 2.docx" });
mainDoc.save("Your Directory Path" + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

 في هذا المثال، قمنا بتعيين رد اتصال لدمج الحقول باستخدام`InsertDocumentAtMailMergeHandler` فئة للتعامل مع إدراج المستند المحدد بواسطة الحقل "Document_1".

## خاتمة

يمكن إجراء استنساخ المستندات ودمجها في Aspose.Words for Java باستخدام تقنيات مختلفة. سواء كنت بحاجة إلى استنساخ مستند، أو إدراج محتوى عند نقاط الاستبدال، أو الإشارات المرجعية، أو أثناء دمج البريد، فإن Aspose.Words يوفر ميزات قوية للتعامل مع المستندات بسلاسة.

## الأسئلة الشائعة

### كيف يمكنني استنساخ مستند في Aspose.Words لـ Java؟

 يمكنك استنساخ مستند في Aspose.Words لـ Java باستخدام`deepClone()` طريقة. هنا مثال:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
Document clone = doc.deepClone();
clone.save("Your Directory Path" + "ClonedDocument.docx");
```

### كيف يمكنني إدراج مستند في إشارة مرجعية؟

 لإدراج مستند في إشارة مرجعية في Aspose.Words for Java، يمكنك العثور على الإشارة المرجعية بالاسم ثم استخدام`insertDocument` طريقة إدراج المحتوى. هنا مثال:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
Document subDoc = new Document("Your Directory Path" + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save("Your Directory Path" + "CombinedDocument.docx");
```

### كيف أقوم بإدراج المستندات أثناء دمج البريد في Aspose.Words لـ Java؟

يمكنك إدراج المستندات أثناء دمج البريد في Aspose.Words for Java عن طريق تعيين رد اتصال لدمج الحقل وتحديد المستند الذي سيتم إدراجه. هنا مثال:

```java
Document mainDoc = new Document("Your Directory Path" + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { "Your Directory Path" + "DocumentToInsert.docx" });
mainDoc.save("Your Directory Path" + "MergedDocument.docx");
```

 في هذا المثال،`InsertDocumentAtMailMergeHandler`يعالج الفصل منطق الإدراج لـ "DocumentField" أثناء دمج المراسلات.