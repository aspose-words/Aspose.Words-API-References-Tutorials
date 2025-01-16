---
title: استخراج المحتوى من المستندات في Aspose.Words للغة Java
linktitle: استخراج المحتوى من المستندات
second_title: واجهة برمجة تطبيقات معالجة المستندات في Java Aspose.Words
description: تعرف على كيفية استخراج المحتوى من المستندات بسهولة باستخدام Aspose.Words for Java. يعمل دليلنا خطوة بخطوة وعينات التعليمات البرمجية لدينا على تبسيط العملية.
type: docs
weight: 13
url: /ar/java/document-manipulation/extracting-content-from-documents/
---

## مقدمة لاستخراج المحتوى من المستندات في Aspose.Words لـ Java

في عالم معالجة المستندات، يعد استخراج المحتوى من المستندات متطلبًا شائعًا. سواء كنت بحاجة إلى استخراج نص أو جداول أو صور أو عناصر مستند معينة، فإن Aspose.Words for Java يوفر أدوات قوية لتسهيل هذه المهمة. في هذا الدليل الشامل، سنرشدك خلال عملية استخراج المحتوى من المستندات باستخدام Aspose.Words for Java. 

## المتطلبات الأساسية

قبل أن نتعمق في عملية الاستخراج، تأكد من توفر المتطلبات الأساسية التالية:

1.  Aspose.Words for Java: يجب أن يكون لديك Aspose.Words for Java مثبتًا ومُعَدًا في بيئة تطوير Java الخاصة بك. يمكنك تنزيله من[هنا](https://releases.aspose.com/words/java/).

2. مستند لاستخراج المحتوى منه: في هذا الدليل، سنستخدم مستندًا نموذجيًا باسم "Extract content.docx". تأكد من أن لديك مستندًا مشابهًا جاهزًا للاستخراج.

## استخراج المحتوى بين العقد على مستوى الكتلة

```java
// عينة من كود Java لاستخراج المحتوى بين العقد على مستوى الكتلة
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getLastSection().getChild(NodeType.PARAGRAPH, 2, true);
Table endTable = (Table) doc.getLastSection().getChild(NodeType.TABLE, 0, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endTable, true);
Collections.reverse(extractedNodes);
while (extractedNodes.size() > 0) {
    endTable.getParentNode().insertAfter((Node) extractedNodes.get(0), endTable);
    extractedNodes.remove(0);
}
doc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBlockLevelNodes.docx");
```

## استخراج المحتوى بين الإشارات المرجعية

```java
//عينة من كود Java لاستخراج المحتوى بين الإشارات المرجعية
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Bookmark bookmark = doc.getRange().getBookmarks().get("Bookmark1");
BookmarkStart bookmarkStart = bookmark.getBookmarkStart();
BookmarkEnd bookmarkEnd = bookmark.getBookmarkEnd();
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.IncludingBookmark.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.WithoutBookmark.docx");
```

## استخراج المحتوى بين نطاقات التعليقات

```java
// عينة من كود Java لاستخراج المحتوى بين نطاقات التعليقات
Document doc = new Document("Your Directory Path" + "Extract content.docx");
CommentRangeStart commentStart = (CommentRangeStart) doc.getChild(NodeType.COMMENT_RANGE_START, 0, true);
CommentRangeEnd commentEnd = (CommentRangeEnd) doc.getChild(NodeType.COMMENT_RANGE_END, 0, true);
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.IncludingComment.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.WithoutComment.docx");
```

## استخراج المحتوى بين الفقرات

```java
// عينة من كود جافا لاستخراج المحتوى بين الفقرات
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
```

## استخراج المحتوى بين أنماط الفقرات

```java
// عينة من كود Java لاستخراج المحتوى بين أنماط الفقرات
Document doc = new Document("Your Directory Path" + "Extract content.docx");
ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
Node startPara1 = parasStyleHeading1.get(0);
Node endPara1 = parasStyleHeading3.get(0);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
```

## استخراج المحتوى بين الجولات

```java
// عينة من أكواد Java لاستخراج المحتوى بين عمليات التشغيل
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
Run startRun = para.getRuns().get(1);
Run endRun = para.getRuns().get(4);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
Node node = (Node) extractedNodes.get(0);
System.out.println(node.toString());
```

## استخراج المحتوى باستخدام DocumentVisitor

```java
// عينة من أكواد Java لاستخراج المحتوى باستخدام DocumentVisitor
Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
doc.accept(myConverter);
System.out.println(myConverter.getText());
```

## استخراج المحتوى باستخدام الحقل

```java
// عينة من كود Java لاستخراج المحتوى باستخدام Field
Document doc = new Document("Your Directory Path" + "Extract content.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.moveToMergeField("Fullname", false, false);
FieldStart startField = (FieldStart) builder.getCurrentNode();
Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
```

## استخراج جدول المحتويات

```java
// عينة من كود جافا لاستخراج جدول المحتويات
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
for (Field field : doc.getRange().getFields()) {
    if (field.getType() == FieldType.FIELD_HYPERLINK) {
        FieldHyperlink hyperlink = (FieldHyperlink) field;
        if (hyperlink.getSubAddress() != null && hyperlink.getSubAddress().startsWith("_Toc")) {
            Paragraph tocItem = (Paragraph) field.getStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(tocItem.toString().trim());
            System.out.println("------------------");
            Bookmark bm = doc.getRange().getBookmarks().get(hyperlink.getSubAddress());
            Paragraph pointer = (Paragraph) bm.getBookmarkStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(pointer.toString());
        }
    }
}
```

## استخراج النص فقط

```java
// عينة من كود جافا لاستخراج النص فقط
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertField("MERGEFIELD Field");
System.out.println("GetText() Result: " + doc.getText());
System.out.println("ToString() Result: " + doc.toString());
```

## استخراج المحتوى بناءً على الأنماط

```java
// عينة من كود Java لاستخراج المحتوى بناءً على الأنماط
Document doc = new Document("Your Directory Path" + "Styles.docx");
final String PARA_STYLE = "Heading 1";
final String RUN_STYLE = "Intense Emphasis";
ArrayList<Paragraph> paragraphs = paragraphsByStyleName(doc, PARA_STYLE);
System.out.println("Paragraphs with \"{paraStyle}\" styles ({paragraphs.Count}):");
for (Paragraph paragraph : paragraphs)
    System.out.println(paragraph.toString(SaveFormat.TEXT));
ArrayList<Run> runs = runsByStyleName(doc, RUN_STYLE);
System.out.println("\nRuns with \"{runStyle}\" styles ({runs.Count}):");
for (Run run : runs)
    System.out.println(run.getRange().getText());
}

public ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}

public ArrayList<Run> runsByStyleName(Document doc, String styleName) {
    ArrayList<Run> runsWithStyle = new ArrayList<Run>();
    NodeCollection runs = doc.getChildNodes(NodeType.RUN, true);
    for (Run run : (Iterable<Run>) runs) {
        if (run.getFont().getStyle().getName().equals(styleName))
            runsWithStyle.add(run);
    }
    return runsWithStyle;
}
```

## استخراج النص وطباعته

```java
// عينة من كود جافا لاستخراج النص وطباعته
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Contents of the table: ");
System.out.println(table.getRange().getText());
System.out.println("\nContents of the row: ");
System.out.println(table.getRows().get(1).getRange().getText());
System.out.println("\nContents of the cell: ");
System.out.println(table.getLastRow().getLastCell().getRange().getText());
```

## استخراج الصور إلى الملفات

```java
// عينة من كود جافا لاستخراج الصور إلى ملفات
Document doc = new Document("Your Directory Path" + "Images.docx");
NodeCollection shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;
for (Shape shape : (Iterable<Shape>) shapes) {
    if (shape.hasImage()) {
        String imageFileName = MessageFormat.format("Image.ExportImages.{0}_{1}",
                imageIndex, FileFormatUtil.imageTypeToExtension(shape.getImageData().getImageType()));
        shape.getImageData().save("Your Directory Path" + imageFileName);
        imageIndex++;
    }
}
```

## خاتمة

تهانينا! لقد تعلمت كيفية استخراج المحتوى من المستندات باستخدام Aspose.Words for Java. غطى هذا الدليل تقنيات الاستخراج المختلفة، بما في ذلك المحتوى بين العقد على مستوى الكتلة، والإشارات المرجعية، ونطاقات التعليقات، والفقرات، والمزيد. أنت الآن مجهز للتعامل مع استخراج محتوى المستندات بكفاءة في تطبيقات Java الخاصة بك.

## الأسئلة الشائعة

### كيف يمكنني استخراج المحتوى من أقسام معينة من المستند؟

لاستخراج المحتوى من أقسام معينة من المستند، يمكنك تحديد نقاط البداية والنهاية للأقسام واستخدام طرق Aspose.Words for Java المناسبة لاستخراج المحتوى بينها.

### هل يمكنني استخراج المحتوى من المستندات المحمية بكلمة مرور؟

نعم، يوفر Aspose.Words for Java وظيفة لاستخراج المحتوى من المستندات المحمية بكلمة مرور. يمكنك توفير كلمة المرور عند فتح المستند باستخدام`Document` منشئ الفئة.

### كيف يمكنني استخراج المحتوى وحفظه بتنسيقات مختلفة، مثل النص العادي أو HTML؟

 يمكنك استخراج المحتوى من مستند وحفظه بتنسيقات مختلفة باستخدام Aspose.Words for Java. بعد استخراج المحتوى، يمكنك استخدام`Document` طرق الفئة لحفظها بتنسيقات مثل النص العادي أو HTML أو غير ذلك.

### هل توجد طريقة لاستخراج المحتوى من عناصر مستند محددة، مثل الجداول أو الصور؟

نعم، يمكنك استخراج المحتوى من عناصر مستند معينة، مثل الجداول أو الصور، باستخدام Aspose.Words for Java. حدد العناصر التي تريد استخراجها، ثم استخدم الطرق المناسبة لاستخراج محتواها.

### كيف يمكنني أتمتة عملية استخراج المحتوى في تطبيق Java الخاص بي؟

لأتمتة عملية استخراج المحتوى في تطبيق Java الخاص بك، يمكنك إنشاء كود مخصص استنادًا إلى التقنيات الموضحة في هذا الدليل. يمكنك أيضًا تنفيذ المنطق لتكرار عملية استخراج المحتوى من مستندات متعددة حسب الحاجة.