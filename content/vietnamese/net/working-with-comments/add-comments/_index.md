---
title: Thêm nhận xét
linktitle: Thêm nhận xét
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm nhận xét vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-comments/add-comments/
---

Trong hướng dẫn toàn diện này, bạn sẽ tìm hiểu cách thêm nhận xét vào tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể chèn nhận xét và tùy chỉnh nội dung của chúng trong tài liệu của mình.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo một tài liệu mới và DocumentBuilder
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document và khởi tạo đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Thêm nội dung vào tài liệu
Tiếp theo, thêm nội dung mong muốn vào tài liệu bằng đối tượng DocumentBuilder. Trong ví dụ này, chúng tôi thêm một số văn bản:

```csharp
builder.Write("Some text is added.");
```

## Bước 3: Tạo bình luận và thêm nội dung
Để thêm nhận xét, hãy tạo một thể hiện của lớp Comment, chuyển đối tượng Document, tên tác giả, tên viết tắt của tác giả và ngày hiện tại:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Tiếp theo, thêm nhận xét vào đoạn hiện tại:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Thêm nội dung vào nhận xét, chẳng hạn như đoạn văn và văn bản:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Bước 4: Lưu tài liệu
Sau khi thêm nhận xét và nội dung của nó, hãy lưu tài liệu vào một tệp bằng phương thức Lưu của lớp Tài liệu:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Mã nguồn ví dụ để thêm nhận xét bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để thêm nhận xét bằng Aspose.Words cho .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm nhận xét vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể chèn nhận xét và tùy chỉnh nội dung của chúng trong tài liệu của mình.

Nhận xét rất hữu ích cho việc cộng tác, cung cấp thông tin bổ sung hoặc ghi chú trong tài liệu. Thử nghiệm với các tên tác giả, tên viết tắt và nội dung nhận xét khác nhau để đáp ứng yêu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể thêm nhận xét vào tài liệu Aspose.Words for .NET?

Đáp: Để thêm nhận xét vào tài liệu Aspose.Words for .NET, bạn cần làm theo các bước được đề cập trong hướng dẫn.

#### Câu hỏi: Tôi có thể định dạng văn bản nhận xét trong Aspose.Words cho .NET không?

Trả lời: Có, bạn có thể định dạng văn bản nhận xét trong Aspose.Words for .NET bằng cách sử dụng các thuộc tính định dạng có sẵn.

#### Câu hỏi: Làm cách nào tôi có thể truy xuất tất cả nhận xét có trong tài liệu?

Trả lời: Bạn có thể truy xuất tất cả các nhận xét có trong tài liệu bằng cách sử dụng`Document.Comments` tài sản.

#### Câu hỏi: Tôi có thể xóa nhận xét cụ thể trong Aspose.Words dành cho .NET không?

 Đáp: Có, bạn có thể xóa một nhận xét cụ thể trong Aspose.Words for .NET bằng cách sử dụng`Comment.Remove` phương pháp.

#### Câu hỏi: Làm cách nào tôi có thể sửa đổi văn bản của nhận xét hiện có trong Aspose.Words cho .NET?

 Trả lời: Để sửa đổi văn bản của nhận xét hiện có trong Aspose.Words cho .NET, bạn có thể truy cập`Comment.Text` thuộc tính tương ứng`Comment` đối tượng và sửa đổi văn bản nếu cần.