---
title: Thêm Xóa Bình luận Trả lời
linktitle: Thêm Xóa Bình luận Trả lời
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm và xóa trả lời nhận xét trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-comments/add-remove-comment-reply/
---

Trong hướng dẫn toàn diện này, bạn sẽ tìm hiểu cách thêm và xóa phản hồi nhận xét trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Khi kết thúc hướng dẫn này, bạn sẽ có thể quản lý các câu trả lời nhận xét và tùy chỉnh chúng theo yêu cầu của mình.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tải tài liệu
Để bắt đầu, hãy tải tài liệu chứa các nhận xét bằng lớp Tài liệu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Bước 2: Truy cập Bình luận và Quản lý câu trả lời
Tiếp theo, truy cập nhận xét từ tài liệu bằng phương thức GetChild với tham số NodeType.Comment:

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

Để xóa câu trả lời khỏi nhận xét, hãy sử dụng phương thức RemoveReply và cung cấp chỉ mục trả lời mong muốn:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

Để thêm câu trả lời mới cho nhận xét, hãy sử dụng phương thức AddReply và cung cấp tên tác giả, tên viết tắt của tác giả, ngày giờ và văn bản trả lời:

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Bước 3: Lưu tài liệu
Sau khi thêm hoặc xóa các câu trả lời nhận xét, hãy lưu tài liệu vào một tệp bằng phương thức Lưu của lớp Tài liệu:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Mã nguồn ví dụ để thêm và xóa câu trả lời nhận xét bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để thêm và xóa phản hồi nhận xét bằng Aspose.Words cho .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm và xóa câu trả lời nhận xét trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể quản lý các câu trả lời nhận xét và tùy chỉnh chúng theo yêu cầu của mình.

Trả lời nhận xét cho phép thảo luận và phản hồi hợp tác trong một tài liệu. Thử nghiệm với các tác giả trả lời, tên viết tắt, ngày tháng và văn bản khác nhau để tăng cường sự cộng tác và giao tiếp trong tài liệu của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể thêm nhận xét trong Aspose.Words cho .NET?

 Đáp: Để thêm nhận xét trong Aspose.Words cho .NET, bạn có thể sử dụng`Comment.AddComment` phương pháp chỉ định văn bản của nhận xét và nơi bạn muốn thêm nó vào tài liệu.

#### Câu hỏi: Làm cách nào để xóa nhận xét trong Aspose.Words dành cho .NET?

 Đáp: Để xóa nhận xét trong Aspose.Words dành cho .NET, bạn có thể sử dụng`Comment.Remove` phương pháp xác định`Comment` đối tượng bạn muốn loại bỏ.

#### Câu hỏi: Tôi có thể trả lời nhận xét trong Aspose.Words cho .NET không?

 Đáp: Có, bạn có thể trả lời nhận xét trong Aspose.Words for .NET bằng cách sử dụng`Comment.AddReply` phương pháp chỉ định văn bản trả lời và nơi bạn muốn thêm nó vào tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể truy cập các nhận xét hiện có trong Aspose.Words cho .NET?

 Trả lời: Bạn có thể truy cập các nhận xét hiện có trong Aspose.Words cho .NET bằng cách sử dụng`CommentCollection` tài sản của`Document`sự vật. Điều này sẽ cho phép bạn duyệt tất cả các nhận xét có trong tài liệu.

#### Câu hỏi: Tôi có thể chỉnh sửa văn bản nhận xét trong Aspose.Words cho .NET không?

 Trả lời: Có, bạn có thể chỉnh sửa nội dung nhận xét trong Aspose.Words for .NET bằng cách truy cập vào`Comment.Text` thuộc tính tương ứng`Comment` đối tượng và sửa đổi văn bản nếu cần.