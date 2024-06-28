---
title: Hình ảnh
linktitle: Hình ảnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn và tùy chỉnh hình ảnh bằng Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/image/
---

Trong ví dụ này, chúng tôi sẽ giải thích cách sử dụng tính năng hình ảnh với Aspose.Words cho .NET. Hình ảnh cho phép bạn chèn hình minh họa và đồ họa vào tài liệu.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Chèn hình ảnh

 Chúng ta có thể chèn một hình ảnh bằng cách sử dụng`Shape` lớp và chỉ định loại hình ảnh, tại đây`ShapeType.Image` . Chúng tôi cũng đặt kiểu bao bọc của hình ảnh thành`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Bước 3: Tùy chỉnh hình ảnh

 Chúng tôi tùy chỉnh hình ảnh bằng cách chỉ định đường dẫn đầy đủ của nó, ví dụ`"/attachment/1456/pic001.png"`và thêm tiêu đề cho hình ảnh.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Mã nguồn ví dụ cho hình ảnh với Aspose.Words for .NET

```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Chèn hình ảnh.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng tính năng hình ảnh với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể chèn hình ảnh từ tệp cục bộ vào Aspose.Words?

 Trả lời: Để chèn hình ảnh từ tệp cục bộ vào Aspose.Words, bạn có thể sử dụng`Shape` lớp học và`InsertImage` phương pháp.

#### Câu hỏi: Tôi có thể chèn hình ảnh từ URL trong Aspose.Words không?

 Trả lời: Có, bạn có thể chèn hình ảnh từ URL trong Aspose.Words. Bạn có thể sử dụng tương tự`InsertImage`phương thức và chỉ định URL hình ảnh thay vì đường dẫn tệp cục bộ.

#### Hỏi: Làm cách nào tôi có thể thay đổi kích thước hình ảnh trong Aspose.Words?

 Trả lời: Để thay đổi kích thước hình ảnh trong Aspose.Words, bạn có thể sử dụng`Width` Và`Height` thuộc tính của`Shape` sự vật.

#### Câu hỏi: Tôi có thể áp dụng bộ lọc cho hình ảnh trong Aspose.Words không?

 Trả lời: Có, bạn có thể áp dụng bộ lọc cho hình ảnh trong Aspose.Words. Ví dụ: bạn có thể áp dụng bộ lọc làm mờ cho hình ảnh bằng cách sử dụng`ApplyGaussianBlur` phương pháp của`Shape` sự vật.

#### Hỏi: Làm cách nào tôi có thể thay thế hình ảnh này bằng hình ảnh khác trong Aspose.Words?

 Trả lời: Để thay thế hình ảnh này bằng hình ảnh khác trong Aspose.Words, bạn có thể sử dụng`Replace` phương pháp của`Shape` lớp học. Phương thức này lấy tham số là`Shape` đối tượng của hình ảnh được thay thế và`Shape` đối tượng của hình ảnh mới.