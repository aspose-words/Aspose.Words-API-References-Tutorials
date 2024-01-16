---
title: Bình luận neo
linktitle: Bình luận neo
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách neo các câu trả lời nhận xét vào văn bản cụ thể trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-comments/anchor-comment/
---

Trong hướng dẫn toàn diện này, bạn sẽ tìm hiểu cách neo các câu trả lời nhận xét vào văn bản cụ thể trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ hướng dẫn bạn thực hiện quy trình và cung cấp cho bạn các đoạn mã C# cần thiết. Đến cuối hướng dẫn này, bạn sẽ có thể liên kết nhận xét với văn bản cụ thể trong tài liệu của mình.

## Điều kiện tiên quyết
Trước khi chúng tôi bắt đầu, hãy đảm bảo rằng bạn có các điều kiện tiên quyết sau:
- Thư viện Aspose.Words for .NET được cài đặt trên hệ thống của bạn.

## Bước 1: Tạo tài liệu mới và thêm văn bản
Để bắt đầu, hãy tạo một tài liệu mới bằng lớp Document và thêm văn bản mong muốn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Bước 2: Tạo bình luận và thêm phạm vi bình luận
Tiếp theo, tạo một nhận xét và liên kết nó với văn bản cụ thể bằng cách sử dụng các đối tượng CommentRangeStart và CommentRangeEnd:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Bước 3: Lưu tài liệu
Sau khi neo nhận xét vào văn bản cụ thể, hãy lưu tài liệu vào một tệp bằng phương thức Lưu của lớp Tài liệu:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Mã nguồn mẫu cho nhận xét neo Trả lời bằng Aspose.Words cho .NET
Đây là mã nguồn hoàn chỉnh để neo câu trả lời nhận xét bằng Aspose.Words cho .NET:

```csharp
// Tạo một phiên bản của Tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Tạo ba đối tượng Run.
// Hai cái đầu tiên chạy một số văn bản, trong khi cái thứ ba chạy Bình luận

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Mỗi đối tượng Run có một đối tượng CommentRangeStart và CommentRangeEnd được liên kết.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Câu hỏi thường gặp

#### Câu hỏi: Neo nhận xét trong Aspose.Words dành cho .NET là gì?

Đáp: Trong Aspose.Words dành cho .NET, neo nhận xét là điểm đánh dấu kết nối nhận xét với một vị trí cụ thể trong tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể thêm neo nhận xét vào tài liệu Aspose.Words cho .NET?

Đáp: Để thêm neo nhận xét vào tài liệu Aspose.Words for .NET, hãy làm theo các bước được đề cập trong hướng dẫn.

#### Câu hỏi: Làm cách nào để truy cập neo nhận xét hiện có trong Aspose.Words cho .NET?

 Trả lời: Bạn có thể truy cập neo nhận xét hiện có trong Aspose.Words dành cho .NET bằng cách sử dụng`Comment.Anchor` tài sản.

#### Câu hỏi: Tôi có thể ưu tiên neo nhận xét trong Aspose.Words cho .NET không?

 Đáp: Có, bạn có thể xóa neo nhận xét trong Aspose.Words dành cho .NET bằng cách sử dụng`Comment.Remove` phương pháp.

#### Câu hỏi: Làm cách nào tôi có thể chỉnh sửa văn bản của nhận xét được liên kết với neo nhận xét trong Aspose.Words cho .NET?

 Trả lời: Để sửa đổi văn bản của một nhận xét được liên kết với một neo nhận xét trong Aspose.Words cho .NET, bạn có thể truy cập vào`Comment.Text` thuộc tính tương ứng`Comment` đối tượng và sửa đổi văn bản nếu cần.

