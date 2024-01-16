---
title: Sử dụng hình mờ cho tài liệu trong Aspose.Words cho Java
linktitle: Sử dụng hình mờ cho tài liệu
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách thêm hình mờ vào tài liệu trong Aspose.Words cho Java. Tùy chỉnh hình mờ văn bản và hình ảnh cho các tài liệu trông chuyên nghiệp.
type: docs
weight: 15
url: /vi/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Giới thiệu về Thêm hình mờ vào tài liệu trong Aspose.Words cho Java

Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm hình mờ vào tài liệu bằng API Aspose.Words cho Java. Hình mờ là một cách hữu ích để gắn nhãn tài liệu bằng văn bản hoặc đồ họa để biểu thị trạng thái, tính bảo mật hoặc thông tin liên quan khác của chúng. Chúng tôi sẽ đề cập đến cả hình mờ văn bản và hình ảnh trong hướng dẫn này.

## Thiết lập Aspose.Words cho Java

Trước khi bắt đầu thêm hình mờ vào tài liệu, chúng ta cần thiết lập Aspose.Words cho Java. Hãy làm theo các bước sau để bắt đầu:

1.  Tải xuống Aspose.Words cho Java từ[đây](https://releases.aspose.com/words/java/).
2. Thêm thư viện Aspose.Words for Java vào dự án Java của bạn.
3. Nhập các lớp cần thiết trong mã Java của bạn.

Bây giờ chúng ta đã thiết lập xong thư viện, hãy tiến hành thêm hình mờ.

## Thêm hình mờ văn bản

Hình mờ văn bản là lựa chọn phổ biến khi bạn muốn thêm thông tin văn bản vào tài liệu của mình. Đây là cách bạn có thể thêm hình mờ văn bản bằng Aspose.Words cho Java:

```java
//Tạo một phiên bản Tài liệu
Document doc = new Document("Document.docx");

// Xác định TextWatermarkOptions
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Đặt văn bản hình mờ và các tùy chọn
doc.getWatermark().setText("Test", options);

// Lưu tài liệu có hình mờ
doc.save("DocumentWithWatermark.docx");
```

## Thêm hình mờ hình ảnh

Ngoài hình mờ văn bản, bạn cũng có thể thêm hình mờ hình ảnh vào tài liệu của mình. Dưới đây là cách thêm hình mờ vào hình ảnh:

```java
//Tạo một phiên bản Tài liệu
Document doc = new Document("Document.docx");

// Tải hình ảnh cho hình mờ
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Đặt kích thước và vị trí hình mờ
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Thêm hình mờ vào tài liệu
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Lưu tài liệu có hình mờ
doc.save("DocumentWithImageWatermark.docx");
```

## Tùy chỉnh hình mờ

Bạn có thể tùy chỉnh hình mờ bằng cách điều chỉnh hình thức và vị trí của chúng. Đối với hình mờ văn bản, bạn có thể thay đổi phông chữ, kích thước, màu sắc và bố cục. Đối với hình mờ trên hình ảnh, bạn có thể sửa đổi kích thước và vị trí của chúng như minh họa trong các ví dụ trước.

## Xóa hình mờ

Để xóa hình mờ khỏi tài liệu, bạn có thể sử dụng đoạn mã sau:

```java
//Tạo một phiên bản Tài liệu
Document doc = new Document("DocumentWithWatermark.docx");

// Xóa hình mờ
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Lưu tài liệu không có hình mờ
doc.save("DocumentWithoutWatermark.docx");
```


## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách thêm hình mờ vào tài liệu bằng Aspose.Words cho Java. Cho dù bạn cần thêm hình mờ văn bản hoặc hình ảnh, Aspose.Words đều cung cấp các công cụ để tùy chỉnh và quản lý chúng một cách hiệu quả. Bạn cũng có thể xóa hình mờ khi không còn cần thiết, đảm bảo tài liệu của bạn sạch sẽ và chuyên nghiệp.

## Câu hỏi thường gặp

### Làm cách nào để thay đổi phông chữ của hình mờ văn bản?

 Để thay đổi phông chữ của hình mờ văn bản, hãy sửa đổi`setFontFamily` tài sản ở`TextWatermarkOptions`. Ví dụ:

```java
options.setFontFamily("Times New Roman");
```

### Tôi có thể thêm nhiều hình mờ vào một tài liệu không?

 Có, bạn có thể thêm nhiều hình mờ vào tài liệu bằng cách tạo nhiều hình mờ`Shape` các đối tượng có cài đặt khác nhau và thêm chúng vào tài liệu.

### Có thể xoay hình mờ?

 Có, bạn có thể xoay hình mờ bằng cách đặt`setRotation` tài sản ở`Shape` sự vật. Các giá trị dương xoay hình mờ theo chiều kim đồng hồ và các giá trị âm xoay hình mờ ngược chiều kim đồng hồ.

### Làm cách nào để tạo hình mờ bán trong suốt?

 Để tạo hình mờ nửa trong suốt, hãy đặt`setSemitransparent`tài sản để`true` bên trong`TextWatermarkOptions`.

### Tôi có thể thêm hình mờ vào các phần cụ thể của tài liệu không?

Có, bạn có thể thêm hình mờ vào các phần cụ thể của tài liệu bằng cách lặp qua các phần và thêm hình mờ vào các phần mong muốn.