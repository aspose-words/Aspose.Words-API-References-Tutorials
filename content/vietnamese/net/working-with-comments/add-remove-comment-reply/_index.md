---
title: Thêm Xóa Bình luận Trả lời
linktitle: Thêm Xóa Bình luận Trả lời
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm và xóa trả lời nhận xét trong tài liệu Word bằng Aspose.Words cho .NET. Nâng cao khả năng cộng tác trên tài liệu của bạn với hướng dẫn từng bước này.
type: docs
weight: 10
url: /vi/net/working-with-comments/add-remove-comment-reply/
---
## Giới thiệu

Làm việc với nhận xét và câu trả lời của họ trong tài liệu Word có thể nâng cao đáng kể quá trình xem xét tài liệu của bạn. Với Aspose.Words for .NET, bạn có thể tự động hóa các tác vụ này, giúp quy trình làm việc của bạn hiệu quả và hợp lý hơn. Hướng dẫn này sẽ hướng dẫn bạn cách thêm và xóa các câu trả lời nhận xét, đồng thời cung cấp hướng dẫn từng bước để làm chủ tính năng này.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET: Tải xuống và cài đặt nó từ[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ IDE nào khác hỗ trợ .NET.
- Kiến thức cơ bản về C#: Cần phải làm quen với lập trình C#.

## Nhập không gian tên

Để bắt đầu, hãy nhập các vùng tên cần thiết trong dự án C# của bạn:

```csharp
using System;
using Aspose.Words;
```

## Bước 1: Tải tài liệu Word của bạn

Trước tiên, bạn cần tải tài liệu Word chứa các bình luận mà bạn muốn quản lý. Trong ví dụ này, chúng tôi giả sử bạn có tài liệu có tên "Comments.docx" trong thư mục của mình.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## Bước 2: Truy cập bình luận đầu tiên

Tiếp theo, truy cập bình luận đầu tiên trong tài liệu. Nhận xét này sẽ là mục tiêu để thêm và xóa các câu trả lời.

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

## Bước 3: Xóa câu trả lời hiện có

Nếu nhận xét đã có câu trả lời, bạn có thể muốn xóa một câu trả lời. Đây là cách bạn có thể xóa câu trả lời đầu tiên của nhận xét:

```csharp
comment.RemoveReply(comment.Replies[0]);
```

## Bước 4: Thêm câu trả lời mới

Bây giờ, hãy thêm một câu trả lời mới cho bình luận. Bạn có thể chỉ định tên tác giả, tên viết tắt, ngày và giờ trả lời cũng như văn bản trả lời.

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## Bước 5: Lưu tài liệu đã cập nhật

Cuối cùng, lưu tài liệu đã sửa đổi vào thư mục của bạn.

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## Phần kết luận

Quản lý các câu trả lời nhận xét trong tài liệu Word theo chương trình có thể giúp bạn tiết kiệm rất nhiều thời gian và công sức, đặc biệt là khi xử lý các bài đánh giá sâu rộng. Aspose.Words for .NET làm cho quá trình này trở nên đơn giản và hiệu quả. Bằng cách làm theo các bước được nêu trong hướng dẫn này, bạn có thể dễ dàng thêm và xóa các câu trả lời nhận xét, nâng cao trải nghiệm cộng tác trên tài liệu của mình.

## Câu hỏi thường gặp

### Làm cách nào để thêm nhiều câu trả lời vào một nhận xét?

 Bạn có thể thêm nhiều câu trả lời cho một nhận xét bằng cách gọi`AddReply` phương thức nhiều lần trên cùng một đối tượng nhận xét.

### Tôi có thể tùy chỉnh chi tiết tác giả cho mỗi câu trả lời không?

 Có, bạn có thể chỉ định tên tác giả, tên viết tắt cũng như ngày và giờ cho mỗi câu trả lời khi sử dụng`AddReply` phương pháp.

### Có thể xóa tất cả các câu trả lời khỏi một bình luận cùng một lúc không?

Để xóa tất cả các câu trả lời, bạn cần lặp qua`Replies` thu thập các bình luận và loại bỏ từng bình luận riêng lẻ.

### Tôi có thể truy cập nhận xét trong một phần cụ thể của tài liệu không?

 Có, bạn có thể điều hướng qua các phần của tài liệu và truy cập nhận xét trong mỗi phần bằng cách sử dụng`GetChild` phương pháp.

### Aspose.Words for .NET có hỗ trợ các tính năng liên quan đến nhận xét khác không?

Có, Aspose.Words for .NET cung cấp hỗ trợ rộng rãi cho nhiều tính năng liên quan đến nhận xét, bao gồm thêm nhận xét mới, đặt thuộc tính nhận xét, v.v.