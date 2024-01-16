---
title: Định dạng bảng và kiểu bảng trong Aspose.Words cho Java
linktitle: Định dạng bảng và kiểu bảng
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách định dạng bảng và áp dụng kiểu bảng trong Aspose.Words cho Java. Khám phá hướng dẫn từng bước với mã nguồn để định dạng bảng hiệu quả. Cải thiện bố cục tài liệu của bạn với Aspose.Words.
type: docs
weight: 17
url: /vi/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Giới thiệu về Định dạng bảng và kiểu bảng trong Aspose.Words cho Java

Bảng đóng một vai trò quan trọng trong việc cấu trúc và tổ chức thông tin trong tài liệu. Aspose.Words for Java cung cấp các tính năng mạnh mẽ để định dạng bảng và áp dụng kiểu bảng nhằm nâng cao sự hấp dẫn trực quan cho tài liệu của bạn. Trong hướng dẫn từng bước này, chúng ta sẽ khám phá các khía cạnh khác nhau của việc định dạng bảng và áp dụng kiểu bảng bằng Aspose.Words cho Java.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào chi tiết, hãy đảm bảo rằng bạn đã tích hợp thư viện Aspose.Words for Java vào dự án của mình. Bạn có thể tải xuống từ trang web Aspose:[Tải xuống Aspose.Words cho Java](https://releases.aspose.com/words/java/).

## Nhận khoảng cách giữa bảng và văn bản xung quanh

Để bắt đầu, hãy khám phá cách lấy khoảng cách giữa bảng và văn bản xung quanh trong tài liệu.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Áp dụng đường viền phác thảo cho bảng

Bạn có thể căn chỉnh bảng vào giữa trang, xóa các đường viền hiện có và đặt đường viền phác thảo tùy chỉnh bằng mã này:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## Xây dựng một bảng có viền

Đoạn mã này trình bày cách tạo bảng và đặt đường viền cho cả bảng và các ô của bảng:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Sửa đổi định dạng hàng

Tìm hiểu cách sửa đổi định dạng của một hàng cụ thể trong bảng:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Áp dụng định dạng hàng

Ví dụ này minh họa cách áp dụng định dạng cho toàn bộ hàng trong bảng:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Đặt phần đệm ô

Khám phá cách đặt phần đệm cho từng ô trong bảng:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Sửa đổi định dạng ô

Khám phá cách sửa đổi định dạng của một ô cụ thể trong bảng:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Định dạng bảng và ô có viền khác nhau

Tìm hiểu cách đặt các đường viền khác nhau cho từng ô trong bảng:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Đặt đường viền cho bảng
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Đặt bóng cho ô riêng lẻ
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Thêm nội dung vào ô
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Xóa định dạng ô cho hàng tiếp theo
builder.getCellFormat().clearFormatting();
// Tạo đường viền lớn hơn cho ô đầu tiên của hàng này
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Đặt tiêu đề và mô tả bảng

Thêm tiêu đề và mô tả vào bảng của bạn:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Bước 10: Cho phép giãn cách ô

Cho phép giãn cách ô và đặt giá trị của nó cho một bảng:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Bước 11: Xây dựng bảng có kiểu dáng

Tạo một bảng với kiểu được xác định trước:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Bước 12: Mở rộng Định dạng trên Ô và Hàng từ Kiểu

Tìm hiểu cách mở rộng kiểu bảng để áp dụng định dạng cho ô và hàng:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Bước 13: Tạo kiểu bảng

Tạo kiểu bảng tùy chỉnh với định dạng cụ thể:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## Bước 14: Xác định định dạng có điều kiện

Áp dụng định dạng có điều kiện cho các hàng trong bảng:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Bước 15: Đặt định dạng TableCell

Đặt định dạng cụ thể cho từng ô:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Bước 16: Đặt định dạng TableRow

Áp dụng định dạng cho toàn bộ hàng trong bảng:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## Phần kết luận

Aspose.Words for Java cho phép bạn định dạng bảng và áp dụng các kiểu bảng một cách chính xác. Từ sửa đổi định dạng ô riêng lẻ đến tạo kiểu bảng tùy chỉnh, bạn có các công cụ để làm cho tài liệu của mình trở nên hấp dẫn và có tổ chức về mặt trực quan.

## Câu hỏi thường gặp

### Làm cách nào để tải xuống Aspose.Words cho Java?

 Bạn có thể tải xuống Aspose.Words cho Java từ trang web Aspose:[Tải xuống Aspose.Words cho Java](https://releases.aspose.com/words/java/).

### Tôi có thể áp dụng các đường viền khác nhau cho từng ô trong bảng không?

Có, bạn có thể đặt các đường viền khác nhau cho từng ô trong bảng bằng Aspose.Words for Java, như được minh họa trong hướng dẫn này.

### Mục đích của việc đặt tiêu đề và mô tả bảng là gì?

Việc đặt tiêu đề và mô tả bảng sẽ nâng cao khả năng truy cập và tổ chức tài liệu của bạn, giúp người đọc và các công nghệ hỗ trợ hiểu nội dung dễ dàng hơn.

### Làm cách nào để áp dụng định dạng có điều kiện cho các hàng cụ thể trong bảng?

Bạn có thể áp dụng định dạng có điều kiện cho các hàng cụ thể trong bảng bằng cách xác định kiểu bảng tùy chỉnh bằng các quy tắc định dạng có điều kiện, như được minh họa trong hướng dẫn này.

### Tôi có thể tìm thêm tài liệu và tài nguyên cho Aspose.Words cho Java ở đâu?

 Để có tài liệu toàn diện và các tài nguyên bổ sung, vui lòng truy cập tài liệu Aspose.Words for Java:[Aspose.Words cho tài liệu Java](https://reference.aspose.com/words/java/).