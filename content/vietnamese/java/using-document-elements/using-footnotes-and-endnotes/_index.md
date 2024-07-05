---
title: Sử dụng chú thích cuối trang và chú thích cuối trong Aspose.Words cho Java
linktitle: Sử dụng chú thích cuối trang và chú thích cuối trang
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách sử dụng chú thích cuối trang và chú thích cuối trang một cách hiệu quả trong Aspose.Words cho Java. Hãy nâng cao kỹ năng định dạng tài liệu của bạn ngay hôm nay!
type: docs
weight: 13
url: /vi/java/using-document-elements/using-footnotes-and-endnotes/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình sử dụng chú thích cuối trang và chú thích cuối trong Aspose.Words cho Java. Chú thích cuối trang và chú thích cuối trang là những thành phần thiết yếu trong định dạng tài liệu, thường được sử dụng để trích dẫn, tài liệu tham khảo và thông tin bổ sung. Aspose.Words for Java cung cấp chức năng mạnh mẽ để làm việc liền mạch với chú thích cuối trang và chú thích cuối trang.

## 1. Giới thiệu về Footnote và Endnote

Chú thích cuối trang và chú thích cuối trang là những chú thích cung cấp thông tin bổ sung hoặc trích dẫn trong tài liệu. Chú thích cuối trang xuất hiện ở cuối trang, trong khi chú thích cuối trang được thu thập ở cuối phần hoặc tài liệu. Chúng thường được sử dụng trong các bài viết học thuật, báo cáo, văn bản pháp luật để tham khảo nguồn hoặc làm rõ nội dung.

## 2. Thiết lập môi trường của bạn

Trước khi chúng ta đi sâu vào làm việc với chú thích cuối trang và chú thích cuối trang, bạn cần thiết lập môi trường phát triển của mình. Đảm bảo bạn đã cài đặt và định cấu hình API Aspose.Words cho Java trong dự án của mình.

## 3. Thêm chú thích cuối trang vào tài liệu của bạn

Để thêm chú thích cuối trang vào tài liệu của bạn, hãy làm theo các bước sau:
```java
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

public void getFootnoteOptions(){
    Document doc = new Document(dataDir + "Document.docx");
    
    // Chỉ định số cột mà khu vực chú thích cuối trang được định dạng.
    doc.getFootnoteOptions().setColumns(3);
    doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
}
```

## 4. Sửa đổi tùy chọn chú thích cuối trang

Bạn có thể sửa đổi các tùy chọn chú thích cuối trang để tùy chỉnh hình thức và hành vi của chúng. Đây là cách thực hiện:
```java
@Test
public void setFootnoteAndEndNotePosition() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    
    doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
    doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
}
```

## 5. Thêm chú thích vào tài liệu của bạn

Việc thêm chú thích cuối vào tài liệu của bạn rất đơn giản. Đây là một ví dụ:
```java
@Test
public void setEndnoteOptions() throws Exception {
    Document doc = new Document(dataDir + "Document.docx");
    DocumentBuilder builder = new DocumentBuilder(doc);
    
    builder.write("Some text");
    builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
    
    EndnoteOptions option = doc.getEndnoteOptions();
    option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
    option.setPosition(EndnotePosition.END_OF_SECTION);
    
    doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
}
```

## 6. Tùy chỉnh cài đặt ghi chú

Bạn có thể tùy chỉnh thêm cài đặt ghi chú cuối để đáp ứng yêu cầu tài liệu của mình.

## Mã nguồn hoàn chỉnh
```java
	string dataDir = "Your Document Directory";
	string outPath = "Your Output Directory";
	public void getFootnoteOptions(){
        Document doc = new Document(dataDir + "Document.docx");
        // Chỉ định số cột mà khu vực chú thích cuối trang được định dạng.
        doc.getFootnoteOptions().setColumns(3);
        doc.save("Your Directory Path" + "WorkingWithFootnotes.SetFootNoteColumns.docx");
    }
    @Test
    public void setFootnoteAndEndNotePosition() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        doc.getFootnoteOptions().setPosition(FootnotePosition.BENEATH_TEXT);
        doc.getEndnoteOptions().setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
    }
    @Test
    public void setEndnoteOptions() throws Exception
    {
        Document doc = new Document(dataDir + "Document.docx");
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.write("Some text");
        builder.insertFootnote(FootnoteType.ENDNOTE, "Footnote text.");
        EndnoteOptions option = doc.getEndnoteOptions();
        option.setRestartRule(FootnoteNumberingRule.RESTART_PAGE);
        option.setPosition(EndnotePosition.END_OF_SECTION);
        doc.save(outPath + "WorkingWithFootnotes.SetEndnoteOptions.docx");
	}
```

## 7. Kết luận

Trong hướng dẫn này, chúng ta đã khám phá cách làm việc với chú thích cuối trang và chú thích cuối trong Aspose.Words cho Java. Những tính năng này rất có giá trị trong việc tạo ra các tài liệu có cấu trúc tốt với các trích dẫn và tài liệu tham khảo thích hợp.

Bây giờ bạn đã học cách sử dụng chú thích cuối trang và chú thích cuối, bạn có thể cải thiện định dạng tài liệu và làm cho nội dung của mình chuyên nghiệp hơn.

### Các câu hỏi thường gặp

### 1. Sự khác biệt giữa chú thích cuối trang và chú thích cuối trang là gì?
Chú thích cuối trang xuất hiện ở cuối trang, trong khi chú thích cuối trang được thu thập ở cuối phần hoặc tài liệu.

### 2. Làm cách nào để thay đổi vị trí của cước chú hoặc chú thích cuối?
 Bạn có thể dùng`setPosition` phương pháp thay đổi vị trí của cước chú hoặc chú thích cuối.

### 3. Tôi có thể tùy chỉnh định dạng của chú thích cuối trang và chú thích cuối sách không?
Có, bạn có thể tùy chỉnh định dạng chú thích cuối trang và chú thích cuối bằng Aspose.Words for Java.

### 4. Chú thích cuối trang và chú thích cuối có quan trọng trong việc định dạng tài liệu không?
Có, chú thích cuối trang và chú thích cuối trang rất cần thiết để cung cấp tài liệu tham khảo và thông tin bổ sung trong tài liệu.

Vui lòng khám phá thêm các tính năng của Aspose.Words cho Java và nâng cao khả năng tạo tài liệu của bạn. Chúc mừng mã hóa!