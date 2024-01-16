---
title: Chèn dấu ngắt trong tài liệu Word
linktitle: Chèn dấu ngắt trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn dấu ngắt trang trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước một.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/insert-break/
---
Trong ví dụ toàn diện này, bạn sẽ tìm hiểu cách chèn ngắt trang vào tài liệu Word bằng phương pháp InsertBreak trong Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể kiểm soát ngắt trang trong tài liệu của mình.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo một tài liệu mới và DocumentBuilder
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document và khởi tạo đối tượng DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn nội dung và ngắt trang
Tiếp theo, sử dụng phương thức Writeln của lớp DocumentBuilder để thêm nội dung vào tài liệu. Để chèn ngắt trang, hãy sử dụng phương thức InsertBreak với tham số BreakType.PageBreak:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Bước 3: Lưu tài liệu
Sau khi chèn nội dung và ngắt trang, lưu tài liệu vào file bằng phương thức Save của lớp Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Mã nguồn ví dụ cho Insert Break sử dụng Aspose.Words for .NET
Đây là mã nguồn hoàn chỉnh để chèn ngắt trang bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

Hãy nhớ điều chỉnh mã theo yêu cầu cụ thể của bạn và nâng cao nó bằng chức năng bổ sung nếu cần.


## Phần kết luận
Chúc mừng! Bạn đã học thành công cách chèn ngắt trang vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể kiểm soát việc phân trang và bố cục tài liệu của mình bằng cách chèn dấu ngắt trang ở các vị trí mong muốn.

### Câu hỏi thường gặp

#### Câu hỏi: Tôi có thể chèn các kiểu ngắt trang khác ngoài ngắt trang không?

Đ: Chắc chắn rồi! Aspose.Words for .NET hỗ trợ nhiều kiểu ngắt trang khác nhau, bao gồm ngắt trang, ngắt cột và ngắt phần. Bạn có thể sử dụng phương thức InsertBreak với các tham số BreakType khác nhau để chèn kiểu ngắt mong muốn.

#### Hỏi: Tôi có thể chèn ngắt trang vào các phần cụ thể của tài liệu không?

Đáp: Có, bạn có thể chèn ngắt trang tại các vị trí cụ thể trong tài liệu. Bằng cách sử dụng DocumentBuilder, bạn có thể kiểm soát vị trí ngắt trang dựa trên nội dung và cấu trúc tài liệu của mình.

#### Hỏi: Các ngắt trang có được giữ nguyên khi lưu tài liệu ở các định dạng tệp khác nhau không?

Trả lời: Có, ngắt trang được chèn bằng Aspose.Words cho .NET được giữ nguyên khi lưu tài liệu ở các định dạng tệp khác nhau, chẳng hạn như DOCX, PDF hoặc RTF. Điều này đảm bảo phân trang và bố cục nhất quán trên các định dạng tệp khác nhau.

#### Hỏi: Tôi có thể tùy chỉnh hình thức ngắt trang không?

Trả lời: Dấu ngắt trang không hiển thị trong chính tài liệu nhưng bạn có thể điều chỉnh định dạng và bố cục của nội dung trước và sau dấu ngắt trang để kiểm soát hình thức của tài liệu.

#### Câu hỏi: Aspose.Words cho .NET có phù hợp cho cả ứng dụng máy tính để bàn và web không?

Trả lời: Có, Aspose.Words for .NET là một thư viện đa năng phù hợp cho cả ứng dụng máy tính để bàn và web. Cho dù bạn đang xây dựng một ứng dụng Windows hay một hệ thống dựa trên web, bạn đều có thể tích hợp thư viện một cách dễ dàng.