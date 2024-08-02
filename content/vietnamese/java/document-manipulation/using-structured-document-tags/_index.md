---
title: Sử dụng Thẻ tài liệu có cấu trúc (SDT) trong Aspose.Words cho Java
linktitle: Sử dụng Thẻ tài liệu có cấu trúc (SDT)
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách sử dụng Thẻ tài liệu có cấu trúc (SDT) trong Aspose.Words cho Java với hướng dẫn toàn diện này. Tạo, sửa đổi và liên kết SDT với dữ liệu XML tùy chỉnh.
type: docs
weight: 19
url: /vi/java/document-manipulation/using-structured-document-tags/
---

## Giới thiệu về cách sử dụng Thẻ tài liệu có cấu trúc (SDT) trong Aspose.Words cho Java

Thẻ tài liệu có cấu trúc (SDT) là một tính năng mạnh mẽ trong Aspose.Words dành cho Java, cho phép bạn tạo và thao tác nội dung có cấu trúc trong tài liệu của mình. Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn các khía cạnh khác nhau của việc sử dụng SDT trong Aspose.Words cho Java. Cho dù bạn là người mới bắt đầu hay nhà phát triển có kinh nghiệm, bạn sẽ tìm thấy những hiểu biết sâu sắc có giá trị và ví dụ thực tế trong bài viết này.

## Bắt đầu

Trước khi đi sâu vào chi tiết, hãy thiết lập môi trường của chúng ta và tạo SDT cơ bản. Trong phần này, chúng tôi sẽ đề cập đến các chủ đề sau:

- Tạo một tài liệu mới
- Thêm thẻ tài liệu có cấu trúc
- Lưu tài liệu

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Tạo Thẻ tài liệu có cấu trúc thuộc loại CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Lưu tài liệu
doc.save("WorkingWithSDT.docx");
```

## Kiểm tra trạng thái hiện tại của hộp kiểm SDT

Khi bạn đã thêm hộp kiểm SDT vào tài liệu của mình, bạn có thể muốn kiểm tra trạng thái hiện tại của nó theo chương trình. Điều này có thể hữu ích khi bạn cần xác thực dữ liệu nhập của người dùng hoặc thực hiện các hành động cụ thể dựa trên trạng thái hộp kiểm.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // Hộp kiểm được chọn
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Sửa đổi kiểm soát nội dung

Trong phần này, chúng ta sẽ khám phá cách sửa đổi các điều khiển nội dung trong tài liệu của bạn. Chúng tôi sẽ đề cập đến ba loại điều khiển nội dung: Văn bản thuần túy, Danh sách thả xuống và Hình ảnh.

### Sửa đổi kiểm soát nội dung văn bản thuần túy

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Xóa nội dung hiện có
    sdtPlainText.removeAllChildren();

    // Thêm văn bản mới
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Sửa đổi kiểm soát nội dung danh sách thả xuống

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Chọn mục thứ hai từ danh sách
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Sửa đổi Kiểm soát Nội dung Hình ảnh

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Thay thế hình ảnh bằng một hình ảnh mới
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Tạo Kiểm soát Nội dung ComboBox

Kiểm soát nội dung ComboBox cho phép người dùng chọn từ danh sách tùy chọn được xác định trước. Hãy tạo một cái trong tài liệu của chúng tôi.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Làm việc với Kiểm soát nội dung văn bản đa dạng thức

Kiểm soát nội dung văn bản đa dạng thức là giải pháp hoàn hảo để thêm văn bản có định dạng vào tài liệu của bạn. Hãy tạo một cái và thiết lập nội dung của nó.

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## Đặt kiểu kiểm soát nội dung

Bạn có thể áp dụng kiểu cho các điều khiển nội dung để nâng cao hình thức trực quan cho tài liệu của mình. Hãy xem cách thiết lập kiểu điều khiển nội dung.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

//Áp dụng kiểu tùy chỉnh
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Liên kết SDT với dữ liệu XML tùy chỉnh

Trong một số trường hợp, bạn có thể cần liên kết SDT với dữ liệu XML tùy chỉnh để tạo nội dung động. Hãy cùng khám phá cách để đạt được điều này.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Tạo một bảng có các phần lặp lại được ánh xạ tới dữ liệu XML tùy chỉnh

Các bảng có các phần lặp lại có thể cực kỳ hữu ích trong việc trình bày dữ liệu có cấu trúc. Hãy tạo một bảng như vậy và ánh xạ nó tới dữ liệu XML tùy chỉnh.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## Làm việc với thẻ tài liệu có cấu trúc nhiều phần

Thẻ tài liệu có cấu trúc có thể trải dài trên nhiều phần trong tài liệu. Trong phần này, chúng ta sẽ khám phá cách làm việc với SDT nhiều phần.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Phần kết luận

Thẻ tài liệu có cấu trúc trong Aspose.Words for Java cung cấp một cách linh hoạt để quản lý và định dạng nội dung trong tài liệu của bạn. Cho dù bạn cần tạo mẫu, biểu mẫu hay tài liệu động, SDT đều mang đến sự linh hoạt và khả năng kiểm soát mà bạn yêu cầu. Bằng cách làm theo các ví dụ và hướng dẫn được cung cấp trong bài viết này, bạn có thể khai thác sức mạnh của SDT để nâng cao các tác vụ xử lý tài liệu của mình.

## Câu hỏi thường gặp

### Mục đích của Thẻ tài liệu có cấu trúc (SDT) là gì?

Thẻ tài liệu có cấu trúc (SDT) phục vụ mục đích tổ chức và định dạng nội dung trong tài liệu, giúp tạo mẫu, biểu mẫu và tài liệu có cấu trúc dễ dàng hơn.

### Làm cách nào tôi có thể kiểm tra trạng thái hiện tại của SDT hộp kiểm?

 Bạn có thể kiểm tra trạng thái hiện tại của SDT hộp kiểm bằng cách sử dụng`setChecked` phương pháp như đã trình bày trong bài viết.

### Tôi có thể áp dụng kiểu cho Kiểm soát nội dung không?

Có, bạn có thể áp dụng kiểu cho Kiểm soát nội dung để tùy chỉnh giao diện của chúng trong tài liệu.

### Có thể liên kết SDT với dữ liệu XML tùy chỉnh không?

Có, bạn có thể liên kết SDT với dữ liệu XML tùy chỉnh, cho phép tạo nội dung động và ánh xạ dữ liệu.

### Các phần lặp lại trong SDT là gì?

Các phần lặp lại trong SDT cho phép bạn tạo các bảng có dữ liệu động, trong đó các hàng có thể được lặp lại dựa trên dữ liệu XML được ánh xạ.