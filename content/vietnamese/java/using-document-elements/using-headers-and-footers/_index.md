---
title: Sử dụng Đầu trang và Chân trang trong Aspose.Words cho Java
linktitle: Sử dụng Đầu trang và Chân trang
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu từng bước cách sử dụng đầu trang và chân trang trong Aspose.Words cho Java. Tạo tài liệu chuyên nghiệp một cách dễ dàng.
type: docs
weight: 16
url: /vi/java/using-document-elements/using-headers-and-footers/
---

Trong hướng dẫn toàn diện này, chúng tôi sẽ hướng dẫn bạn quy trình làm việc với đầu trang và chân trang trong Aspose.Words cho Java. Đầu trang và chân trang là những thành phần thiết yếu trong định dạng tài liệu và Aspose.Words cung cấp các công cụ mạnh mẽ để tạo và tùy chỉnh chúng theo nhu cầu của bạn.

Bây giờ, hãy đi sâu vào từng bước một cách chi tiết.

## 1. Giới thiệu về Aspose.Words

Aspose.Words là một API Java mạnh mẽ cho phép bạn tạo, thao tác và hiển thị tài liệu Word theo chương trình. Nó cung cấp các tính năng mở rộng để định dạng tài liệu, bao gồm đầu trang và chân trang.

## 2. Thiết lập môi trường Java của bạn

 Trước khi bạn bắt đầu sử dụng Aspose.Words, hãy đảm bảo rằng bạn đã thiết lập chính xác môi trường phát triển Java của mình. Bạn có thể tìm thấy hướng dẫn thiết lập cần thiết trên trang tài liệu Aspose.Words:[Tài liệu Java Aspose.Words](https://reference.aspose.com/words/java/).

## 3. Tạo một tài liệu mới

Để làm việc với đầu trang và chân trang, bạn cần tạo một tài liệu mới bằng Aspose.Words. Đoạn mã sau đây minh họa cách thực hiện việc này:

```java
// Mã Java để tạo một tài liệu mới
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Tìm hiểu cách thiết lập trang

 Thiết lập trang rất quan trọng để kiểm soát bố cục tài liệu của bạn. Bạn có thể chỉ định các thuộc tính khác nhau liên quan đến đầu trang và chân trang bằng cách sử dụng`PageSetup` lớp học. Ví dụ:

```java
// Thiết lập thuộc tính trang
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. Đầu trang/chân trang đầu tiên khác nhau

Aspose.Words cho phép bạn có các đầu trang và chân trang khác nhau cho trang đầu tiên của tài liệu. Sử dụng`pageSetup.setDifferentFirstPageHeaderFooter(true);` để kích hoạt tính năng này.

## 6. Làm việc với tiêu đề

### 6.1. Thêm văn bản vào tiêu đề

 Bạn có thể thêm văn bản vào tiêu đề bằng cách sử dụng`DocumentBuilder`. Đây là một ví dụ:

```java
// Thêm văn bản vào tiêu đề trang đầu tiên
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Chèn hình ảnh vào tiêu đề

 Để chèn hình ảnh vào tiêu đề, bạn có thể sử dụng`insertImage` phương pháp. Đây là một ví dụ:

```java
// Chèn hình ảnh vào tiêu đề
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Tùy chỉnh kiểu tiêu đề

Bạn có thể tùy chỉnh kiểu tiêu đề bằng cách đặt các thuộc tính khác nhau như phông chữ, căn chỉnh, v.v., như được hiển thị trong các ví dụ ở trên.

## 7. Làm việc với chân trang

### 7.1. Thêm văn bản vào chân trang

 Tương tự như đầu trang, bạn có thể thêm văn bản vào chân trang bằng cách sử dụng`DocumentBuilder`. Đây là một ví dụ:

```java
// Thêm văn bản vào chân trang chính
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// Chèn văn bản và các trường nếu cần
```

### 7.2. Chèn hình ảnh vào Footer

 Để chèn hình ảnh vào chân trang, hãy sử dụng`insertImage` phương thức, giống như trong các tiêu đề.

### 7.3. Tùy chỉnh kiểu chân trang

 Tùy chỉnh kiểu chân trang bằng cách sử dụng`DocumentBuilder`tương tự như tùy chỉnh tiêu đề.

## 8. Đánh số trang

 Bạn có thể bao gồm số trang trong đầu trang và chân trang bằng các trường như`PAGE` Và`NUMPAGES`. Các trường này tự động cập nhật khi bạn thêm hoặc xóa trang.

## 9. Thông tin bản quyền ở Footers

Để thêm thông tin bản quyền vào chân trang tài liệu của bạn, bạn có thể sử dụng một bảng có hai ô, căn chỉnh một ô sang trái và ô kia sang phải, như minh họa trong đoạn mã.

## 10. Làm việc với nhiều phần

Aspose.Words cho phép bạn làm việc với nhiều phần trong một tài liệu. Bạn có thể đặt các thiết lập trang và đầu trang/chân trang khác nhau cho từng phần.

## 11. Định hướng cảnh quan

Bạn có thể thay đổi hướng của các phần cụ thể sang chế độ ngang nếu cần.

## 12. Sao chép Đầu trang/Chân trang từ các Phần trước

Sao chép đầu trang và chân trang từ các phần trước có thể tiết kiệm thời gian khi tạo các tài liệu phức tạp.

## 13. Lưu tài liệu của bạn

Sau khi tạo và tùy chỉnh tài liệu của bạn, đừng quên lưu nó bằng cách sử dụng`doc.save()` phương pháp.

## Mã nguồn hoàn chỉnh
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // Chỉ định xem chúng tôi có muốn đầu trang/chân trang của trang đầu tiên khác với các trang khác hay không.
        // Bạn cũng có thể sử dụng thuộc tính PageSetup.OddAndEvenPagesHeaderFooter để chỉ định
        // đầu trang/chân trang khác nhau cho các trang chẵn và lẻ.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Chèn hình ảnh được định vị vào góc trên/trái của tiêu đề.
        // Khoảng cách từ cạnh trên/trái của trang được đặt thành 10 điểm.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // Chúng ta sử dụng bảng có hai ô để tạo thành một phần văn bản trên dòng (có đánh số trang).
        // Để được căn trái và phần còn lại của văn bản (có bản quyền) được căn phải.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Nó sử dụng các trường TRANG và SỐ để tự động tính toán số trang hiện tại và nhiều trang.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Thực hiện ngắt trang để tạo trang thứ hai trên đó sẽ nhìn thấy đầu trang/chân trang chính.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Phần này không cần đầu trang/chân trang khác của trang đầu tiên, chúng tôi chỉ cần một trang tiêu đề trong tài liệu,
        //và đầu trang/chân trang cho trang này đã được xác định ở phần trước.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // Phần này hiển thị đầu trang/chân trang từ phần trước
        // theo mặc định, hãy gọi currentSection.HeadersFooters.LinkToPrevious(false) để hủy độ rộng trang này
        // khác với phần mới và do đó chúng ta cần đặt độ rộng ô khác nhau cho bảng chân trang.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Nếu chúng ta muốn sử dụng bộ đầu trang/chân trang đã có sẵn cho phần này.
        // Nhưng với một số sửa đổi nhỏ, việc sao chép đầu trang/chân trang có thể sẽ hữu ích hơn
        // từ phần trước và áp dụng các sửa đổi cần thiết ở nơi chúng tôi muốn.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
Mã nguồn của phương thức copyHeadersFootersFromPreviousSection
```java
    /// <tóm tắt>
    /// Sao chép và sao chép đầu trang/chân trang từ phần trước sang phần được chỉ định.
    /// </tóm tắt>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày những kiến thức cơ bản về cách làm việc với đầu trang và chân trang trong Aspose.Words cho Java. Bạn đã học cách tạo, tùy chỉnh và tạo kiểu cho đầu trang và chân trang cũng như các kỹ thuật định dạng tài liệu cần thiết khác.

 Để biết thêm chi tiết và các tính năng nâng cao, hãy tham khảo[Tài liệu Java Aspose.Words](https://reference.aspose.com/words/java/).

## Câu hỏi thường gặp

### 1. Làm cách nào để thêm số trang vào chân trang tài liệu của tôi?
 Bạn có thể thêm số trang bằng cách chèn`PAGE` vào phần chân trang bằng Aspose.Words.

### 2. Aspose.Words có tương thích với môi trường phát triển Java không?
Có, Aspose.Words cung cấp hỗ trợ cho việc phát triển Java. Đảm bảo bạn có sẵn các thiết lập cần thiết.

### 3. Tôi có thể tùy chỉnh phông chữ và kiểu dáng của đầu trang và chân trang không?
Hoàn toàn có thể, bạn có thể tùy chỉnh phông chữ, căn chỉnh và các kiểu khác để làm cho đầu trang và chân trang của bạn trở nên hấp dẫn về mặt trực quan.

### 4. Có thể đặt tiêu đề khác nhau cho trang chẵn và trang lẻ không?
 Có, bạn có thể sử dụng`PageSetup.OddAndEvenPagesHeaderFooter` để chỉ định các tiêu đề khác nhau cho các trang chẵn và lẻ.

### 5. Làm cách nào để bắt đầu với Aspose.Words cho Java?
 Để bắt đầu, hãy truy cập[Tài liệu Java Aspose.Words](https://reference.aspose.com/words/java/) để được hướng dẫn toàn diện về cách sử dụng API.