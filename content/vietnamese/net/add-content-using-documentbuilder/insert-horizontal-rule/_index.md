---
title: Chèn thước ngang vào tài liệu Word
linktitle: Chèn thước ngang vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn quy tắc ngang trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước một.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/insert-horizontal-rule/
---
Trong ví dụ toàn diện này, bạn sẽ tìm hiểu cách chèn quy tắc ngang vào tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể thêm các quy tắc ngang vào tài liệu của mình để sắp xếp và phân tách trực quan.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo một tài liệu mới và DocumentBuilder
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document và khởi tạo đối tượng DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn thước ngang
Tiếp theo, sử dụng phương thức Writeln của lớp DocumentBuilder để thêm văn bản mô tả rồi chèn quy tắc ngang:

```csharp
builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();
```

## Bước 3: Lưu tài liệu
Sau khi chèn thước ngang, lưu tài liệu vào file bằng phương thức Save của lớp Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

### Mã nguồn ví dụ để chèn quy tắc ngang bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để chèn quy tắc ngang bằng Aspose.Words cho .NET:
Quy tắc ngang rất hữu ích cho nhiều tình huống khác nhau, chẳng hạn như chia phần, tạo dấu ngắt trực quan hoặc làm nổi bật thông tin quan trọng.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Insert a horizontal rule shape into the document.");
builder.InsertHorizontalRule();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
```

Hãy nhớ điều chỉnh mã theo yêu cầu cụ thể của bạn và nâng cao nó bằng chức năng bổ sung nếu cần.

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách chèn thước ngang vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể phân tách và sắp xếp tài liệu của mình một cách trực quan bằng cách sử dụng các quy tắc ngang.

### Hỏi đáp chèn thước ngang vào văn bản word

#### Câu hỏi: Tôi có thể tùy chỉnh hình thức của thước ngang không?

Đ: Vâng, hoàn toàn có thể! Aspose.Words for .NET cung cấp nhiều thuộc tính khác nhau để tùy chỉnh giao diện của quy tắc ngang. Bạn có thể điều chỉnh chiều rộng, chiều cao, căn chỉnh, màu sắc và độ bóng của nó để phù hợp với tính thẩm mỹ của tài liệu.

#### Câu hỏi: Tôi có thể thêm nhiều quy tắc ngang vào một tài liệu không?

Đ: Chắc chắn rồi! Bạn có thể chèn bao nhiêu quy tắc ngang nếu cần trong tài liệu Word bằng Aspose.Words for .NET. Chỉ cần lặp lại quá trình chèn để thêm nhiều dấu ngắt trực quan hoặc bộ chia phần.

#### Hỏi: Các quy tắc ngang có tương thích với các định dạng tệp khác như PDF không?

Trả lời: Có, các quy tắc ngang được chèn bằng Aspose.Words cho .NET tương thích với nhiều định dạng tệp khác nhau, bao gồm DOCX và PDF. Điều này có nghĩa là bạn có thể xuất tài liệu của mình ở các định dạng khác nhau trong khi vẫn giữ nguyên các quy tắc theo chiều ngang.

#### Câu hỏi: Tôi có thể chèn quy tắc ngang theo chương trình vào các vị trí cụ thể trong tài liệu không?

Đ: Chắc chắn rồi! Aspose.Words for .NET cho phép bạn định vị quy tắc ngang tại các vị trí cụ thể trong tài liệu theo chương trình. Bạn có thể kiểm soát vị trí của nó dựa trên nội dung và cấu trúc tài liệu của bạn.

#### Câu hỏi: Aspose.Words cho .NET có phù hợp cho cả ứng dụng máy tính để bàn và web không?

Trả lời: Có, Aspose.Words for .NET rất linh hoạt và có thể được sử dụng trong cả ứng dụng web và máy tính để bàn. Cho dù bạn đang xây dựng một ứng dụng Windows hay một hệ thống dựa trên web, bạn đều có thể tích hợp thư viện một cách dễ dàng.