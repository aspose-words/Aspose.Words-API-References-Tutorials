---
title: Tạo mục lục trong Aspose.Words cho Java
linktitle: Tạo mục lục
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách tạo và tùy chỉnh Mục lục (TOC) bằng Aspose.Words cho Java. Tạo các tài liệu có tổ chức và chuyên nghiệp một cách dễ dàng.
type: docs
weight: 21
url: /vi/java/document-manipulation/generating-table-of-contents/
---

## Giới thiệu về tạo mục lục trong Aspose.Words cho Java

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo Mục lục (TOC) bằng Aspose.Words cho Java. TOC là một tính năng quan trọng để tạo các tài liệu có tổ chức. Chúng tôi sẽ đề cập đến cách tùy chỉnh giao diện và bố cục của TOC.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập Aspose.Words for Java trong dự án Java của mình.

## Bước 1: Tạo một tài liệu mới

Đầu tiên, hãy tạo một tài liệu mới để làm việc.

```java
Document doc = new Document();
```

## Bước 2: Tùy chỉnh kiểu TOC

Để tùy chỉnh giao diện TOC của bạn, bạn có thể sửa đổi các kiểu liên quan đến nó. Trong ví dụ này, chúng tôi sẽ in đậm các mục TOC cấp một.

```java
doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_1).getFont().setBold(true);
```

## Bước 3: Thêm nội dung vào tài liệu của bạn

Bạn có thể thêm nội dung của bạn vào tài liệu. Nội dung này sẽ được sử dụng để tạo TOC.

## Bước 4: Tạo TOC

Để tạo TOC, hãy chèn trường TOC vào vị trí mong muốn trong tài liệu của bạn. Trường này sẽ tự động điền dựa trên các tiêu đề và kiểu trong tài liệu của bạn.

```java
// Chèn trường TOC vào vị trí mong muốn trong tài liệu của bạn.
FieldToc fieldToc = new FieldToc();
doc.getFirstSection().getBody().getFirstParagraph().appendChild(fieldToc);
```

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu với TOC.

```java
doc.save("your_output_path_here");
```

## Tùy chỉnh điểm dừng tab trong TOC

Bạn cũng có thể tùy chỉnh các điểm dừng tab trong TOC của mình để kiểm soát bố cục số trang. Đây là cách bạn có thể thay đổi điểm dừng tab:

```java
Document doc = new Document("Table of contents.docx");

for (Paragraph para : (Iterable<Paragraph>) doc.getChildNodes(NodeType.PARAGRAPH, true))
{
    if (para.getParagraphFormat().getStyle().getStyleIdentifier() >= StyleIdentifier.TOC_1 &&
        para.getParagraphFormat().getStyle().getStyleIdentifier() <= StyleIdentifier.TOC_9)
    {
        //Lấy tab đầu tiên được sử dụng trong đoạn này để căn chỉnh số trang.
        TabStop tab = para.getParagraphFormat().getTabStops().get(0);
        
        // Xóa tab cũ.
        para.getParagraphFormat().getTabStops().removeByPosition(tab.getPosition());
        
        // Chèn một tab mới vào vị trí đã sửa đổi (ví dụ: 50 đơn vị sang trái).
        para.getParagraphFormat().getTabStops().add(tab.getPosition() - 50.0, tab.getAlignment(), tab.getLeader());
    }
}

doc.save("output.docx");
```

Giờ đây, bạn đã có Mục lục tùy chỉnh trong tài liệu của mình với các điểm dừng tab được điều chỉnh để căn chỉnh số trang.


## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách tạo Mục lục (TOC) bằng Aspose.Words cho Java, một thư viện mạnh mẽ để làm việc với tài liệu Word. TOC có cấu trúc tốt là điều cần thiết để tổ chức và điều hướng các tài liệu dài và Aspose.Words cung cấp các công cụ để tạo và tùy chỉnh TOC một cách dễ dàng.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi định dạng của mục TOC?

 Bạn có thể sửa đổi các kiểu liên quan đến mức TOC bằng cách sử dụng`doc.getStyles().getByStyleIdentifier(StyleIdentifier.TOC_X)`, trong đó X là mức TOC.

### Làm cách nào tôi có thể thêm nhiều cấp độ hơn vào TOC của mình?

Để bao gồm nhiều cấp độ hơn trong TOC của bạn, bạn có thể sửa đổi trường TOC và chỉ định số cấp độ mong muốn.

### Tôi có thể thay đổi vị trí điểm dừng tab cho các mục TOC cụ thể không?

Có, như trong ví dụ về mã ở trên, bạn có thể thay đổi vị trí điểm dừng tab cho các mục TOC cụ thể bằng cách lặp qua các đoạn văn và sửa đổi điểm dừng tab cho phù hợp.