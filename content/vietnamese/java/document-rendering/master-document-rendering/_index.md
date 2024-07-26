---
title: Kết xuất tài liệu chính
linktitle: Kết xuất tài liệu chính
second_title: API xử lý tài liệu Java Aspose.Words
description: 
type: docs
weight: 10
url: /vi/java/document-rendering/master-document-rendering/
---

Trong hướng dẫn từng bước toàn diện này, chúng ta sẽ đi sâu vào thế giới kết xuất tài liệu và xử lý văn bản bằng Aspose.Words cho Java. Kết xuất tài liệu là một khía cạnh quan trọng của nhiều ứng dụng, cho phép người dùng xem và thao tác tài liệu một cách liền mạch. Cho dù bạn đang làm việc trên hệ thống quản lý nội dung, công cụ báo cáo hay bất kỳ ứng dụng tập trung vào tài liệu nào thì việc hiểu cách hiển thị tài liệu là điều cần thiết. Trong suốt hướng dẫn này, chúng tôi sẽ cung cấp cho bạn kiến thức và mã nguồn mà bạn cần để thành thạo việc kết xuất tài liệu bằng Aspose.Words cho Java.

## Giới thiệu về kết xuất tài liệu

Kết xuất tài liệu là quá trình chuyển đổi tài liệu điện tử thành dạng trình bày trực quan để người dùng xem, chỉnh sửa hoặc in. Nó liên quan đến việc dịch nội dung, bố cục và định dạng của tài liệu sang định dạng phù hợp, chẳng hạn như PDF, XPS hoặc hình ảnh, trong khi vẫn giữ nguyên cấu trúc và hình thức ban đầu của tài liệu. Trong bối cảnh phát triển Java, Aspose.Words là một thư viện mạnh mẽ cho phép bạn làm việc với nhiều định dạng tài liệu khác nhau và hiển thị chúng một cách liền mạch cho người dùng.

Kết xuất tài liệu là một phần quan trọng của các ứng dụng hiện đại xử lý nhiều loại tài liệu. Cho dù bạn đang tạo trình chỉnh sửa tài liệu dựa trên web, hệ thống quản lý tài liệu hay công cụ báo cáo, việc thành thạo kết xuất tài liệu sẽ nâng cao trải nghiệm người dùng và hợp lý hóa các quy trình lấy tài liệu làm trung tâm.

## Bắt đầu với Aspose.Words cho Java

Trước khi đi sâu vào kết xuất tài liệu, hãy bắt đầu với Aspose.Words cho Java. Hãy làm theo các bước sau để thiết lập thư viện và bắt đầu làm việc với nó:

### Cài đặt và thiết lập

Để sử dụng Aspose.Words cho Java, bạn cần đưa tệp JAR Aspose.Words vào dự án Java của mình. Bạn có thể tải xuống JAR từ Bản phát hành Aspose(https://releases.aspose.com/words/java/) và thêm nó vào đường dẫn lớp của dự án của bạn.

### Cấp phép Aspose.Words cho Java

 Để sử dụng Aspose.Words cho Java trong môi trường sản xuất, bạn phải có giấy phép hợp lệ. Nếu không có giấy phép, thư viện sẽ hoạt động ở chế độ đánh giá, với một số hạn chế. Bạn có thể có được một[giấy phép](https://purchase.aspose.com/pricing) và áp dụng nó để khai thác toàn bộ tiềm năng của thư viện.

## Tải và thao tác tài liệu

Sau khi thiết lập Aspose.Words cho Java, bạn có thể bắt đầu tải và thao tác tài liệu. Aspose.Words hỗ trợ nhiều định dạng tài liệu khác nhau, chẳng hạn như DOCX, DOC, RTF, HTML, v.v. Bạn có thể tải những tài liệu này vào bộ nhớ và truy cập nội dung của chúng theo chương trình.

### Đang tải các định dạng tài liệu khác nhau

Để tải tài liệu, hãy sử dụng lớp Tài liệu do Aspose.Words cung cấp. Lớp Tài liệu cho phép bạn mở tài liệu từ luồng, tệp hoặc URL.

```java
// Tải tài liệu từ một tập tin
Document doc = new Document("path/to/document.docx");

// Tải tài liệu từ luồng
InputStream stream = new FileInputStream("path/to/document.docx");
Document doc = new Document(stream);

// Tải tài liệu từ một URL
Document doc = new Document("https://example.com/document.docx");
```

### Truy cập nội dung tài liệu

Sau khi tài liệu được tải, bạn có thể truy cập nội dung, đoạn văn, bảng, hình ảnh và các thành phần khác bằng API phong phú của Aspose.Words.

```java
// Truy cập đoạn văn
NodeCollection<Paragraph> paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);

// Truy cập bảng
NodeCollection<Table> tables = doc.getChildNodes(NodeType.TABLE, true);

// Truy cập hình ảnh
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
```

### Sửa đổi các thành phần tài liệu

Aspose.Words cho phép bạn thao tác các thành phần tài liệu theo chương trình. Bạn có thể sửa đổi văn bản, định dạng, bảng và các thành phần khác để điều chỉnh tài liệu theo yêu cầu của bạn.

```java
// Sửa đổi văn bản trong một đoạn văn
Paragraph firstParagraph = (Paragraph) paragraphs.get(0);
firstParagraph.getRuns().get(0).setText("Hello, World!");

// Chèn một đoạn văn mới
Paragraph newParagraph = new Paragraph(doc);
newParagraph.appendChild(new Run(doc, "This is a new paragraph."));
doc.getFirstSection().getBody().appendChild(newParagraph);
```

## Làm việc với bố cục tài liệu

Hiểu bố cục tài liệu là điều cần thiết để hiển thị chính xác. Aspose.Words cung cấp các công cụ mạnh mẽ để kiểm soát và điều chỉnh bố cục tài liệu của bạn.

### Điều chỉnh cài đặt trang

Bạn có thể tùy chỉnh cài đặt trang như lề, kích thước giấy, hướng và đầu trang/chân trang bằng cách sử dụng lớp PageSetup.

```java
// Đặt lề trang
PageSetup pageSetup = doc.getFirstSection().getPageSetup();
pageSetup.setLeftMargin(50);
pageSetup.setRightMargin(50);
pageSetup.setTopMargin(30);
pageSetup.setBottomMargin(30);

// Đặt kích thước và hướng giấy
pageSetup.setPaperSize(PaperSize.A4);
pageSetup.setOrientation(Orientation.LANDSCAPE);

// Thêm đầu trang và chân trang
pageSetup.setHeaderDistance(20);
pageSetup.setFooterDistance(10);
pageSetup.setHeaderFooter(HeaderFooterType.HEADER_PRIMARY, new Paragraph(doc, "Header Text"));
pageSetup.setHeaderFooter(HeaderFooterType.FOOTER_PRIMARY, new Paragraph(doc, "Footer Text"));
```

### Đầu trang và chân trang

Đầu trang và chân trang cung cấp thông tin nhất quán trên các trang tài liệu. Bạn có thể thêm nội dung khác nhau vào đầu trang và chân trang chính, trang đầu tiên và thậm chí là lẻ/chẵn.

```java
// Thêm nội dung vào tiêu đề chính
HeaderFooter primaryHeader = pageSetup.getHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
Paragraph headerPara = new Paragraph(doc, "This is the header text.");
primaryHeader.appendChild(headerPara);

// Thêm nội dung vào chân trang chính
HeaderFooter primaryFooter = pageSetup.getHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
Paragraph footerPara = new Paragraph(doc, "Page number: ");
FieldPage fieldPage = new FieldPage();
footerPara.appendChild(fieldPage);
primaryFooter.appendChild(footerPara);
```

## Kết xuất tài liệu

Khi bạn đã xử lý và sửa đổi tài liệu, đã đến lúc hiển thị nó thành nhiều định dạng đầu ra khác nhau. Aspose.Words hỗ trợ hiển thị sang PDF, XPS, hình ảnh và các định dạng khác.

### Hiển thị sang các định dạng đầu ra khác nhau

Để hiển thị một tài liệu, bạn cần sử dụng phương thức lưu của lớp Tài liệu và chỉ định định dạng đầu ra mong muốn.

```java
// Kết xuất thành PDF
doc.save("output.pdf", SaveFormat.PDF);

// Kết xuất sang XPS
doc.save("output.xps", SaveFormat.XPS);

// Kết xuất thành hình ảnh
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setResolution(300);
doc.save("output.png", saveOptions);
```

### Xử lý việc thay thế phông chữ

Việc thay thế phông chữ có thể xảy ra nếu tài liệu chứa các phông chữ không có sẵn trên hệ thống đích. Aspose.Words cung cấp lớp FontSettings để xử lý việc thay thế phông chữ.

```java
// Bật tính năng thay thế phông chữ
FontSettings fontSettings = new FontSettings();
fontSettings.setFontsFolder("path/to/fonts/folder", true);
doc.setFontSettings(fontSettings);
```

### Kiểm soát chất lượng hình ảnh đầu ra

Khi hiển thị tài liệu sang định dạng hình ảnh, bạn có thể kiểm soát chất lượng hình ảnh để tối ưu hóa kích thước và độ rõ nét của tệp.

```java
// Đặt tùy chọn hình ảnh
ImageSaveOptions imageOptions = new ImageSaveOptions(SaveFormat.PNG);
imageOptions.setResolution(300);
imageOptions.setPrettyFormat(true);
doc.save("output.png", imageOptions);
```

## Kỹ thuật kết xuất nâng cao

Aspose.Words cung cấp các kỹ thuật nâng cao để hiển thị các phần cụ thể của tài liệu, có thể hữu ích cho các tài liệu lớn hoặc các yêu cầu cụ thể.

### Hiển thị các trang tài liệu cụ thể

Bạn có thể hiển thị các trang cụ thể của tài liệu, cho phép bạn hiển thị các phần cụ thể hoặc tạo bản xem trước một cách hiệu quả.

```java
// Hiển thị phạm vi trang cụ thể
int startPage = 3;
int endPage = 5;
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(startPage, endPage));
doc.save("output.png", saveOptions);
```

### Kết xuất phạm vi tài liệu

Nếu bạn chỉ muốn hiển thị các phần cụ thể của tài liệu, chẳng hạn như đoạn văn hoặc phần, Aspose.Words cung cấp khả năng thực hiện điều đó.

```java
// Hiển thị các đoạn cụ thể
int[] paragraphIndices = {0, 2, 4};
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(paragraphIndices));
doc.save("output.png", saveOptions);
```

### Kết xuất các phần tử tài liệu riêng lẻ

Để kiểm soát chi tiết hơn, bạn có thể hiển thị các thành phần tài liệu riêng lẻ như bảng hoặc hình ảnh.

```java
// Kết xuất bảng cụ thể
int tableIndex = 1;
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.PNG);
saveOptions.setPageSet(new PageSet(tableIndex));
doc.save("output.png", saveOptions);
```


## Phần kết luận

Nắm vững cách kết xuất tài liệu là điều cần thiết để xây dựng các ứng dụng mạnh mẽ có thể xử lý tài liệu một cách hiệu quả. Với Aspose.Words cho Java, bạn có sẵn một bộ công cụ mạnh mẽ để thao tác và hiển thị tài liệu một cách liền mạch. Trong suốt hướng dẫn này, chúng tôi đã đề cập đến các khái niệm cơ bản về kết xuất tài liệu, làm việc với bố cục tài liệu, kết xuất sang các định dạng đầu ra khác nhau và các kỹ thuật kết xuất nâng cao. Bằng cách sử dụng API mở rộng của Aspose.Words cho Java, bạn có thể tạo các ứng dụng tập trung vào tài liệu hấp dẫn mang lại trải nghiệm người dùng vượt trội.

## Câu hỏi thường gặp

### Sự khác biệt giữa hiển thị tài liệu và xử lý tài liệu là gì?

Kết xuất tài liệu liên quan đến việc chuyển đổi tài liệu điện tử thành dạng trình bày trực quan để người dùng xem, chỉnh sửa hoặc in, trong khi xử lý tài liệu bao gồm các tác vụ như trộn thư, chuyển đổi và bảo vệ.

### Aspose.Words có tương thích với tất cả các phiên bản Java không?

Aspose.Words for Java hỗ trợ Java phiên bản 1.6 trở lên.

### Tôi có thể chỉ hiển thị các trang cụ thể của một tài liệu lớn không?

Có, bạn có thể sử dụng Aspose.Words để hiển thị các trang hoặc phạm vi trang cụ thể một cách hiệu quả.

### Làm cách nào để bảo vệ tài liệu được hiển thị bằng mật khẩu?

Aspose.Words cho phép bạn áp dụng bảo vệ bằng mật khẩu cho các tài liệu được hiển thị để bảo mật nội dung của chúng.

### Aspose.Words có thể hiển thị tài liệu bằng nhiều ngôn ngữ không?

Có, Aspose.Words hỗ trợ hiển thị tài liệu bằng nhiều ngôn ngữ khác nhau và xử lý liền mạch văn bản với các mã hóa ký tự khác nhau.