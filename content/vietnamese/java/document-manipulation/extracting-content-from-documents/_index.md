---
title: Trích xuất nội dung từ tài liệu trong Aspose.Words cho Java
linktitle: Trích xuất nội dung từ tài liệu
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách trích xuất nội dung từ tài liệu một cách dễ dàng bằng Aspose.Words cho Java. Hướng dẫn từng bước và mẫu mã của chúng tôi giúp đơn giản hóa quy trình.
type: docs
weight: 13
url: /vi/java/document-manipulation/extracting-content-from-documents/
---

## Giới thiệu về trích xuất nội dung từ tài liệu trong Aspose.Words cho Java

Trong thế giới xử lý tài liệu, việc trích xuất nội dung từ tài liệu là một yêu cầu phổ biến. Cho dù bạn cần trích xuất văn bản, bảng, hình ảnh hay các thành phần tài liệu cụ thể, Aspose.Words for Java đều cung cấp các công cụ mạnh mẽ để thực hiện công việc này một cách dễ dàng. Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình trích xuất nội dung từ tài liệu bằng Aspose.Words cho Java. 

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào quá trình trích xuất, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Words for Java: Bạn nên cài đặt và thiết lập Aspose.Words for Java trong môi trường phát triển Java của mình. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/java/).

2. Tài liệu để trích xuất nội dung từ: Đối với hướng dẫn này, chúng tôi sẽ sử dụng tài liệu mẫu có tên "Trích xuất nội dung.docx." Hãy chắc chắn rằng bạn có sẵn một tài liệu tương tự để trích xuất.

## Trích xuất nội dung giữa các nút cấp khối

```java
// Mẫu mã Java để trích xuất nội dung giữa các nút cấp khối
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

## Trích xuất nội dung giữa các dấu trang

```java
//Mẫu mã Java để trích xuất nội dung giữa các dấu trang
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

## Trích xuất nội dung giữa các phạm vi nhận xét

```java
// Mẫu mã Java để trích xuất nội dung giữa các phạm vi nhận xét
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

## Trích xuất nội dung giữa các đoạn văn

```java
// Mẫu mã Java để trích xuất nội dung giữa các đoạn văn
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
```

## Trích xuất nội dung giữa các kiểu đoạn văn

```java
// Mẫu mã Java để trích xuất nội dung giữa các kiểu đoạn văn
Document doc = new Document("Your Directory Path" + "Extract content.docx");
ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
Node startPara1 = parasStyleHeading1.get(0);
Node endPara1 = parasStyleHeading3.get(0);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
```

## Trích xuất nội dung giữa các lần chạy

```java
// Mẫu mã Java để trích xuất nội dung giữa các lần chạy
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
Run startRun = para.getRuns().get(1);
Run endRun = para.getRuns().get(4);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
Node node = (Node) extractedNodes.get(0);
System.out.println(node.toString(SaveFormat.TEXT));
```

## Trích xuất nội dung bằng DocumentVisitor

```java
// Mẫu mã Java để trích xuất nội dung bằng DocumentVisitor
Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
doc.accept(myConverter);
System.out.println(myConverter.getText());
```

## Trích xuất nội dung bằng trường

```java
// Mẫu mã Java để trích xuất nội dung bằng Field
Document doc = new Document("Your Directory Path" + "Extract content.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.moveToMergeField("Fullname", false, false);
FieldStart startField = (FieldStart) builder.getCurrentNode();
Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
```

## Trích xuất mục lục

```java
// Mẫu mã Java để trích xuất mục lục
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
for (Field field : doc.getRange().getFields()) {
    if (field.getType() == FieldType.FIELD_HYPERLINK) {
        FieldHyperlink hyperlink = (FieldHyperlink) field;
        if (hyperlink.getSubAddress() != null && hyperlink.getSubAddress().startsWith("_Toc")) {
            Paragraph tocItem = (Paragraph) field.getStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(tocItem.toString(SaveFormat.TEXT).trim());
            System.out.println("------------------");
            Bookmark bm = doc.getRange().getBookmarks().get(hyperlink.getSubAddress());
            Paragraph pointer = (Paragraph) bm.getBookmarkStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(pointer.toString(SaveFormat.TEXT));
        }
    }
}
```

## Chỉ trích xuất văn bản

```java
// Mẫu mã Java chỉ để trích xuất văn bản
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertField("MERGEFIELD Field");
System.out.println("GetText() Result: " + doc.getText());
System.out.println("ToString() Result: " + doc.toString(SaveFormat.TEXT));
```

## Trích xuất nội dung dựa trên kiểu

```java
// Mẫu mã Java để trích xuất nội dung dựa trên kiểu
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

## Trích xuất và in văn bản

```java
// Mẫu mã Java để trích xuất và in văn bản
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Contents of the table: ");
System.out.println(table.getRange().getText());
System.out.println("\nContents of the row: ");
System.out.println(table.getRows().get(1).getRange().getText());
System.out.println("\nContents of the cell: ");
System.out.println(table.getLastRow().getLastCell().getRange().getText());
```

## Trích xuất hình ảnh vào tập tin

```java
// Mẫu mã Java để trích xuất hình ảnh vào tệp
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

## Phần kết luận

Chúc mừng! Bạn đã học cách trích xuất nội dung từ tài liệu bằng Aspose.Words cho Java. Hướng dẫn này đề cập đến các kỹ thuật trích xuất khác nhau, bao gồm nội dung giữa các nút cấp khối, dấu trang, phạm vi nhận xét, đoạn văn, v.v. Bây giờ bạn đã được trang bị để xử lý việc trích xuất nội dung tài liệu một cách hiệu quả trong các ứng dụng Java của mình.

## Câu hỏi thường gặp

### Làm cách nào để trích xuất nội dung từ các phần tài liệu cụ thể?

Để trích xuất nội dung từ các phần tài liệu cụ thể, bạn có thể xác định điểm bắt đầu và điểm kết thúc của các phần và sử dụng các phương thức Aspose.Words for Java thích hợp để trích xuất nội dung giữa chúng.

### Tôi có thể trích xuất nội dung từ các tài liệu được bảo vệ bằng mật khẩu không?

Có, Aspose.Words for Java cung cấp chức năng trích xuất nội dung từ các tài liệu được bảo vệ bằng mật khẩu. Bạn có thể cung cấp mật khẩu khi mở tài liệu bằng cách sử dụng`Document` hàm tạo lớp.

### Làm cách nào tôi có thể trích xuất nội dung và lưu nó ở các định dạng khác nhau, chẳng hạn như văn bản thuần túy hoặc HTML?

 Bạn có thể trích xuất nội dung từ một tài liệu và lưu nó ở các định dạng khác nhau bằng Aspose.Words cho Java. Sau khi trích xuất nội dung, bạn có thể sử dụng`Document` các phương thức lớp để lưu nó ở các định dạng như văn bản thuần túy, HTML hoặc các định dạng khác.

### Có cách nào để trích xuất nội dung từ các thành phần tài liệu cụ thể, chẳng hạn như bảng hoặc hình ảnh không?

Có, bạn có thể trích xuất nội dung từ các thành phần tài liệu cụ thể, chẳng hạn như bảng hoặc hình ảnh, bằng cách sử dụng Aspose.Words for Java. Xác định các phần tử bạn muốn trích xuất, sau đó sử dụng các phương pháp thích hợp để trích xuất nội dung của chúng.

### Làm cách nào tôi có thể tự động hóa quá trình trích xuất nội dung trong ứng dụng Java của mình?

Để tự động hóa quy trình trích xuất nội dung trong ứng dụng Java, bạn có thể tạo mã tùy chỉnh dựa trên các kỹ thuật được mô tả trong hướng dẫn này. Bạn cũng có thể triển khai logic để lặp qua nhiều tài liệu và trích xuất nội dung nếu cần.