---
title: Chèn ảnh nổi vào tài liệu Word
linktitle: Chèn ảnh nổi vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn hình ảnh nổi trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước một.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/insert-floating-image/
---
Trong ví dụ toàn diện này, bạn sẽ tìm hiểu cách chèn hình ảnh nổi vào tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể thêm hình ảnh với các tùy chọn định vị và gói có thể tùy chỉnh vào tài liệu của mình.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo một tài liệu mới và DocumentBuilder
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document và khởi tạo đối tượng DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn hình ảnh nổi
Tiếp theo, sử dụng phương thức InsertImage của lớp DocumentBuilder để chèn hình ảnh nổi. Cung cấp đường dẫn tệp hình ảnh, vị trí ngang và dọc tương đối, chiều rộng, chiều cao và các tùy chọn gói dưới dạng tham số:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);
```

## Bước 3: Lưu tài liệu
Sau khi chèn ảnh nổi, lưu tài liệu vào file bằng phương thức Save của lớp Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

## Mã nguồn ví dụ để chèn hình ảnh nổi bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để chèn hình ảnh nổi bằng Aspose.Words cho .NET:
Hình ảnh nổi rất hữu ích cho nhiều trường hợp khác nhau, chẳng hạn như thêm biểu tượng, hình minh họa hoặc các thành phần trang trí có thể được định vị độc lập với văn bản của tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png",
	RelativeHorizontalPosition.Margin,
	100,
	RelativeVerticalPosition.Margin,
	100,
	200,
	100,
	WrapType.Square);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
```

Hãy nhớ điều chỉnh mã theo yêu cầu cụ thể của bạn, bao gồm đường dẫn tệp hình ảnh cũng như các tùy chọn định vị và gói mong muốn.

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách chèn hình ảnh nổi vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể nâng cao tài liệu của mình bằng các hình ảnh nổi hấp dẫn và có thể tùy chỉnh trực quan.

### Hỏi đáp chèn ảnh nổi vào văn bản word

#### Câu hỏi: Tôi có thể chèn nhiều hình ảnh nổi vào một tài liệu không?

Đ: Chắc chắn rồi! Bạn có thể chèn bao nhiêu hình ảnh nổi nếu cần vào tài liệu Word bằng Aspose.Words for .NET. Chỉ cần lặp lại quá trình chèn để thêm nhiều hình ảnh hấp dẫn trực quan.

#### Câu hỏi: Có những tùy chọn gói nào cho hình ảnh nổi?

Đáp: Aspose.Words for .NET cung cấp nhiều tùy chọn gói khác nhau cho hình ảnh nổi, bao gồm Square, Tight, Through, TopBottom và None. Các tùy chọn này xác định cách văn bản tương tác với hình ảnh nổi.

#### Hỏi: Tôi có thể điều chỉnh kích thước của hình ảnh nổi không?

Đ: Chắc chắn rồi! Bạn có thể chỉ định chiều rộng và chiều cao của hình ảnh nổi bằng các tham số tương ứng trong phương thức InsertImage. Điều này cho phép bạn kiểm soát kích thước của hình ảnh theo sở thích thiết kế của bạn.

#### Câu hỏi: Tôi có thể định vị hình ảnh nổi tương ứng với một thành phần cụ thể trong tài liệu không?

Đáp: Có, Aspose.Words for .NET cho phép bạn định vị hình ảnh nổi tương ứng với các thành phần cụ thể, chẳng hạn như lề, trang, đoạn văn hoặc bảng. Bạn có thể chọn các tham số vị trí ngang và dọc tương đối thích hợp để đạt được vị trí mong muốn.

#### Câu hỏi: Aspose.Words cho .NET có phù hợp cho cả ứng dụng máy tính để bàn và web không?

Trả lời: Có, Aspose.Words for .NET là một thư viện đa năng phù hợp cho cả ứng dụng máy tính để bàn và web. Cho dù bạn đang xây dựng một ứng dụng Windows hay một hệ thống dựa trên web, bạn đều có thể tích hợp thư viện một cách dễ dàng.
