---
title: Chèn hình ảnh nội tuyến vào tài liệu Word
linktitle: Chèn hình ảnh nội tuyến vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn hình ảnh nội tuyến vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/insert-inline-image/
---
Trong hướng dẫn toàn diện này, bạn sẽ tìm hiểu cách chèn hình ảnh nội tuyến vào tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể thêm hình ảnh trực tiếp vào văn bản tài liệu của mình.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo một tài liệu mới và DocumentBuilder
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document và khởi tạo đối tượng DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn hình ảnh nội tuyến
Tiếp theo, sử dụng phương thức InsertImage của lớp DocumentBuilder để chèn hình ảnh nội tuyến vào tài liệu. Cung cấp đường dẫn tệp hình ảnh làm tham số:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Bước 3: Lưu tài liệu
Sau khi chèn hình ảnh nội tuyến, hãy lưu tài liệu vào một tệp bằng phương thức Lưu của lớp Tài liệu:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Mã nguồn ví dụ để chèn hình ảnh nội tuyến bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để chèn hình ảnh nội tuyến bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách chèn hình ảnh nội tuyến vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể thêm hình ảnh một cách liền mạch vào văn bản tài liệu của mình.

Hình ảnh nội tuyến hữu ích cho nhiều trường hợp khác nhau, chẳng hạn như thêm hình minh họa, biểu tượng hoặc các thành phần trực quan khác trực tiếp vào luồng tài liệu.

### Câu hỏi thường gặp về chèn hình ảnh nội tuyến vào tài liệu word

#### Hỏi: Tôi có thể thay đổi kích thước hình ảnh nội tuyến trong tài liệu Word không?

Trả lời: Có, bạn có thể thay đổi kích thước hình ảnh nội tuyến bằng Aspose.Words cho .NET. Sau khi chèn hình ảnh, bạn có thể thao tác với kích thước của nó bằng cách điều chỉnh thuộc tính chiều rộng và chiều cao của đối tượng Shape đại diện cho hình ảnh.

#### Câu hỏi: Có thể thêm văn bản thay thế vào hình ảnh nội tuyến nhằm mục đích trợ năng không?

Đáp: Có, bạn có thể thêm văn bản thay thế vào hình ảnh nội tuyến để nâng cao khả năng truy cập. Aspose.Words for .NET hỗ trợ thêm văn bản thay thế vào hình ảnh, cho phép trình đọc màn hình và các công nghệ hỗ trợ khác mô tả nội dung hình ảnh cho người dùng khiếm thị.

#### Câu hỏi: Tôi có thể áp dụng định dạng hoặc kiểu cho hình ảnh nội tuyến không?

Đ: Chắc chắn rồi! Aspose.Words for .NET cung cấp các tùy chọn định dạng mở rộng cho hình ảnh nội tuyến. Bạn có thể áp dụng nhiều kiểu, đường viền, hiệu ứng và thuộc tính định dạng khác cho hình ảnh để phù hợp với thiết kế trực quan của tài liệu.

#### Câu hỏi: Aspose.Words for .NET có hỗ trợ chèn hình ảnh từ luồng hoặc mảng byte không?

Trả lời: Có, bạn có thể chèn hình ảnh nội tuyến từ luồng hoặc mảng byte bằng Aspose.Words cho .NET. Điều này cho phép bạn làm việc với hình ảnh được tải từ nguồn bên ngoài hoặc hình ảnh được tạo động.

#### Hỏi: Tôi có thể chèn hình ảnh vào những vị trí cụ thể trong nội dung văn bản được không?

Đáp: Có, lớp DocumentBuilder trong Aspose.Words for .NET cung cấp khả năng kiểm soát chính xác đối với vị trí chèn của hình ảnh nội tuyến. Bạn có thể chỉ định vị trí chính xác trong văn bản nơi hình ảnh sẽ được chèn.