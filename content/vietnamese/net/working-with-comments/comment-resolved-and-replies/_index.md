---
title: Bình luận đã được giải quyết và trả lời
linktitle: Bình luận đã được giải quyết và trả lời
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách giải quyết các nhận xét và câu trả lời của chúng trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-comments/comment-resolved-and-replies/
---

Trong hướng dẫn toàn diện này, bạn sẽ tìm hiểu cách giải quyết các nhận xét và câu trả lời của chúng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Khi kết thúc hướng dẫn này, bạn sẽ có thể quản lý việc giải quyết nhận xét và cập nhật trạng thái của nhận xét cũng như câu trả lời của họ.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tải tài liệu và truy cập nhận xét
Để bắt đầu, hãy tải tài liệu chứa các nhận xét bằng lớp Tài liệu và truy cập bộ sưu tập nhận xét:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## Bước 2: Giải quyết nhận xét và câu trả lời của họ
Tiếp theo, lặp lại các nhận xét và câu trả lời của chúng để đánh dấu chúng là đã giải quyết:

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

Trong đoạn mã trên, chúng ta truy cập vào nhận xét gốc và lặp lại các câu trả lời của nhận xét đó. Chúng tôi có thể truy xuất ID nhận xét gốc và trạng thái giải quyết của nó. Sau đó, chúng tôi cập nhật dấu "Xong" của mỗi câu trả lời nhận xét để cho biết cách giải quyết.

## Bước 3: Lưu tài liệu
Sau khi giải quyết các nhận xét và cập nhật trạng thái của chúng, hãy lưu tài liệu đã sửa đổi vào một tệp bằng phương thức Lưu của lớp Tài liệu:

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Mã nguồn ví dụ để giải quyết nhận xét và câu trả lời của họ bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để giải quyết các nhận xét và phản hồi của chúng bằng Aspose.Words cho .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
Hãy nhớ điều chỉnh mã theo yêu cầu cụ thể của bạn, bao gồm đường dẫn tệp tài liệu và tùy chỉnh bổ sung

## Phần kết luận
Chúc mừng! Bạn đã học thành công cách giải quyết các nhận xét và câu trả lời của chúng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, giờ đây bạn có thể quản lý độ phân giải nhận xét cũng như cập nhật trạng thái nhận xét cũng như câu trả lời của chúng theo yêu cầu của bạn.

Độ phân giải nhận xét giúp theo dõi và quản lý phản hồi trong tài liệu. Thử nghiệm với các trạng thái nhận xét khác nhau và tùy chỉnh chúng để cải thiện quy trình cộng tác và đánh giá trong tài liệu của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để giải quyết nhận xét trong Aspose.Words dành cho .NET?

 Đáp: Để giải quyết một nhận xét trong Aspose.Words dành cho .NET, bạn có thể sử dụng`Comment.Resolve` phương pháp xác định`Comment` đối tượng bạn muốn giải quyết. Điều này sẽ đánh dấu nhận xét là đã được giải quyết và ẩn nó trong tài liệu cuối cùng.

#### Câu hỏi: Làm cách nào để thêm câu trả lời cho nhận xét đã được giải quyết trong Aspose.Words cho .NET?

 Đáp: Mặc dù các nhận xét đã giải quyết bị ẩn theo mặc định trong tài liệu cuối cùng, bạn vẫn có thể thêm câu trả lời cho nhận xét đã giải quyết bằng cách sử dụng`Comment.AddReply`phương pháp chỉ định văn bản trả lời và nơi bạn muốn thêm nó.

#### Câu hỏi: Làm cách nào để xem các nhận xét đã được giải quyết trong Aspose.Words dành cho .NET?

 Đáp: Theo mặc định, các nhận xét đã giải quyết sẽ bị ẩn trong tài liệu cuối cùng. Tuy nhiên, bạn có thể hiển thị chúng bằng cách sử dụng`CommentOptions.ShowResolvedComments` tài sản của`Document` đối tượng và đặt nó thành`true`.

#### Câu hỏi: Làm cách nào tôi có thể ẩn tất cả nhận xét, bao gồm cả câu trả lời, trong Aspose.Words dành cho .NET?

 Trả lời: Để ẩn tất cả nhận xét, bao gồm cả câu trả lời, trong Aspose.Words dành cho .NET, bạn có thể sử dụng`CommentOptions.CommentDisplayMode` tài sản của`Document` đối tượng và đặt nó thành`CommentDisplayMode.None`.

#### Câu hỏi: Tôi có thể chỉnh sửa nội dung của nhận xét đã được giải quyết trong Aspose.Words cho .NET không?

 Trả lời: Có, bạn có thể chỉnh sửa nội dung của nhận xét đã được giải quyết trong Aspose.Words for .NET bằng cách truy cập vào`Comment.Text` thuộc tính tương ứng`Comment` đối tượng và sửa đổi văn bản nếu cần.