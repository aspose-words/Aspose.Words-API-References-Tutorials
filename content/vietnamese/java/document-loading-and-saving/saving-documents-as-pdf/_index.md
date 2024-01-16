---
title: Lưu tài liệu dưới dạng PDF trong Aspose.Words cho Java
linktitle: Lưu tài liệu dưới dạng PDF
second_title: API xử lý tài liệu Java Aspose.Words
description: Tìm hiểu cách lưu tài liệu Word dưới dạng PDF bằng Aspose.Words cho Java. Tùy chỉnh phông chữ, thuộc tính và chất lượng hình ảnh. Hướng dẫn toàn diện để chuyển đổi PDF.
type: docs
weight: 22
url: /vi/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Giới thiệu về Lưu tài liệu dưới dạng PDF trong Aspose.Words cho Java

Trong hướng dẫn từng bước này, chúng ta sẽ khám phá cách lưu tài liệu dưới dạng PDF bằng Aspose.Words cho Java. Chúng tôi sẽ đề cập đến các khía cạnh khác nhau của việc chuyển đổi PDF và cung cấp các ví dụ về mã để giúp quá trình này dễ dàng hơn.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:

- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Aspose.Words cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/words/java/).

## Chuyển đổi tài liệu sang PDF

Để chuyển đổi tài liệu Word sang PDF, bạn có thể sử dụng đoạn mã sau:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Thay thế`"input.docx"` với đường dẫn đến tài liệu Word của bạn và`"output.pdf"` với đường dẫn tệp PDF đầu ra mong muốn.

## Kiểm soát các tùy chọn lưu PDF

 Bạn có thể kiểm soát các tùy chọn lưu PDF khác nhau bằng cách sử dụng`PdfSaveOptions` lớp học. Ví dụ: bạn có thể đặt tiêu đề hiển thị cho tài liệu PDF như sau:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## Nhúng phông chữ trong PDF

Để nhúng phông chữ vào tệp PDF được tạo, hãy sử dụng mã sau:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## Tùy chỉnh thuộc tính tài liệu

Bạn có thể tùy chỉnh các thuộc tính tài liệu trong tệp PDF được tạo. Ví dụ:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## Xuất cấu trúc tài liệu

 Để xuất cấu trúc tài liệu, hãy đặt`exportDocumentStructure` tùy chọn để`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## Nén hình ảnh

Bạn có thể kiểm soát việc nén hình ảnh bằng mã sau:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## Cập nhật thuộc tính được in lần cuối

Để cập nhật thuộc tính "Được in lần cuối" trong tệp PDF, hãy sử dụng:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## Hiển thị hiệu ứng 3D DML

Để hiển thị nâng cao các hiệu ứng DML 3D, hãy đặt chế độ hiển thị:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## Hình ảnh nội suy

Bạn có thể bật tính năng nội suy hình ảnh để cải thiện chất lượng hình ảnh:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## Phần kết luận

Aspose.Words for Java cung cấp khả năng toàn diện để chuyển đổi tài liệu Word sang định dạng PDF với các tùy chọn linh hoạt và tùy chỉnh. Bạn có thể kiểm soát các khía cạnh khác nhau của đầu ra PDF, bao gồm phông chữ, thuộc tính tài liệu, nén hình ảnh, v.v.

## Câu hỏi thường gặp

### Làm cách nào để chuyển đổi tài liệu Word sang PDF bằng Aspose.Words cho Java?

Để chuyển đổi tài liệu Word sang PDF, hãy sử dụng đoạn mã sau:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Thay thế`"input.docx"` với đường dẫn đến tài liệu Word của bạn và`"output.pdf"` với đường dẫn tệp PDF đầu ra mong muốn.

### Tôi có thể nhúng phông chữ vào tệp PDF do Aspose.Words tạo cho Java không?

 Có, bạn có thể nhúng phông chữ vào tệp PDF bằng cách đặt`setEmbedFullFonts` tùy chọn để`true` TRONG`PdfSaveOptions`. Đây là một ví dụ:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### Làm cách nào tôi có thể tùy chỉnh các thuộc tính tài liệu trong tệp PDF được tạo?

 Bạn có thể tùy chỉnh các thuộc tính tài liệu trong PDF bằng cách sử dụng`setCustomPropertiesExport` tùy chọn trong`PdfSaveOptions`. Ví dụ:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Mục đích của việc nén hình ảnh trong Aspose.Words cho Java là gì?

 Nén hình ảnh cho phép bạn kiểm soát chất lượng và kích thước hình ảnh trong tệp PDF được tạo. Bạn có thể đặt chế độ nén ảnh bằng cách sử dụng`setImageCompression` TRONG`PdfSaveOptions`.

### Làm cách nào để cập nhật thuộc tính "Bản in cuối cùng" trong PDF?

 Bạn có thể cập nhật thuộc tính "Được TRONGlần cuối" trong tệp PDF bằng cách cài đặt`setUpdateLastPrintedProperty` ĐẾN`true` in `PdfSaveOptions`. Điều này sẽ phản ánh ngày in cuối cùng trong siêu dữ liệu PDF.

### Làm cách nào để cải thiện chất lượng hình ảnh khi chuyển đổi sang PDF?

 Để cải thiện chất lượng hình ảnh, hãy bật tính năng nội suy hình ảnh bằng cách cài đặt`setInterpolateImages` ĐẾN`true` TRONG`PdfSaveOptions`. Điều này sẽ mang lại hình ảnh mượt mà hơn và chất lượng cao hơn trong tệp PDF.