---
title: Chấp nhận sửa đổi
linktitle: Chấp nhận sửa đổi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chấp nhận bản sửa đổi đối với tài liệu Word bằng Aspose.Words cho .NET
type: docs
weight: 10
url: /vi/net/working-with-revisions/accept-revisions/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách chấp nhận các bản sửa đổi đối với tài liệu Word bằng cách sử dụng tính năng Chấp nhận bản sửa đổi của Aspose.Words cho .NET. Thực hiện theo các bước bên dưới để hiểu mã nguồn và chấp nhận các thay đổi đối với tài liệu.

## Bước 1: Thêm và chỉnh sửa nội dung tài liệu

Trong ví dụ này, chúng tôi đang tạo một tài liệu và thêm nội dung. Chúng tôi sử dụng một số đoạn văn để minh họa những thay đổi và sửa đổi. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Thêm văn bản vào đoạn đầu tiên, sau đó thêm hai đoạn văn nữa.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2.");
body.AppendParagraph("Paragraph 3.");
```

## Bước 2: Theo dõi đánh giá và thêm đánh giá

Chúng tôi kích hoạt tính năng theo dõi sửa đổi và thêm bản sửa đổi vào tài liệu. Đây là cách thực hiện:

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Đoạn này là một bản sửa đổi và sẽ có bộ cờ "IsInsertRevision" tương ứng.
para = body.AppendParagraph("Paragraph 4.");
Assert.True(para.IsInsertRevision);
```

## Bước 3: Xóa một đoạn văn và quản lý các bản sửa đổi

Chúng tôi xóa một đoạn văn và kiểm tra các bản sửa đổi đã lưu. Đây là cách thực hiện:

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Vì chúng tôi đang theo dõi các bản sửa đổi nên đoạn văn vẫn tồn tại trong tài liệu nên sẽ có cờ "IsDeleteRevision" được đặt
// và sẽ được hiển thị dưới dạng bài đánh giá trong Microsoft Word cho đến khi chúng tôi chấp nhận hoặc từ chối tất cả các bài đánh giá.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);
```

## Bước 4: Chấp nhận thay đổi

Chúng tôi chấp nhận mọi thay đổi đối với tài liệu. Đây là cách thực hiện:

```csharp
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
```

## Bước 5: Dừng theo dõi đánh giá

Chúng tôi sẽ ngừng theo dõi các bản sửa đổi để những thay đổi đối với tài liệu không còn hiển thị dưới dạng bản sửa đổi nữa. Đây là cách thực hiện:

```csharp
doc.StopTrackRevisions();
```
## Bước 6: Lưu tài liệu

 Sau khi chèn trường biểu mẫu nhập văn bản, hãy lưu tài liệu vào vị trí mong muốn bằng cách sử dụng`Save`phương pháp. Đảm bảo cung cấp đường dẫn tệp thích hợp:

```csharp
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```

### Mã nguồn mẫu cho Chấp nhận bản sửa đổi bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để chấp nhận các thay đổi trong tài liệu bằng Aspose.Words cho .NET:


```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

// Thêm văn bản vào đoạn đầu tiên, sau đó thêm hai đoạn văn nữa.
para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

//Chúng tôi có ba đoạn, không có đoạn nào được đăng ký là bất kỳ loại sửa đổi nào
// Nếu chúng tôi thêm/xóa bất kỳ nội dung nào trong tài liệu trong khi theo dõi các bản sửa đổi,
// chúng sẽ được hiển thị như vậy trong tài liệu và có thể được chấp nhận/từ chối.
doc.StartTrackRevisions("John Doe", DateTime.Now);

// Đoạn này là một bản sửa đổi và sẽ có cờ "IsInsertRevision" được đặt tương ứng.
para = body.AppendParagraph("Paragraph 4. ");
Assert.True(para.IsInsertRevision);

// Lấy bộ sưu tập đoạn văn của tài liệu và xóa một đoạn văn.
ParagraphCollection paragraphs = body.Paragraphs;
Assert.AreEqual(4, paragraphs.Count);
para = paragraphs[2];
para.Remove();

// Vì chúng tôi đang theo dõi các bản sửa đổi nên đoạn văn vẫn tồn tại trong tài liệu nên sẽ có tập hợp "IsDeleteRevision"
// và sẽ được hiển thị dưới dạng bản sửa đổi trong Microsoft Word cho đến khi chúng tôi chấp nhận hoặc từ chối tất cả các bản sửa đổi.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Đoạn sửa đổi xóa sẽ bị xóa khi chúng tôi chấp nhận thay đổi.
doc.AcceptAllRevisions();
Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);

// Việc dừng theo dõi các bản sửa đổi sẽ làm cho văn bản này xuất hiện dưới dạng văn bản bình thường.
// Các sửa đổi không được tính khi tài liệu được thay đổi.
doc.StopTrackRevisions();

// Lưu tài liệu.
doc.Save(dataDir + "WorkingWithRevisions.AcceptRevisions.docx");
```
## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách chấp nhận các bản sửa đổi trong tài liệu Word bằng tính năng Chấp nhận bản sửa đổi của Aspose.Words cho .NET. Chúng tôi đã làm theo các bước để thêm và chỉnh sửa nội dung tài liệu, theo dõi các bản sửa đổi, xóa đoạn sửa đổi, chấp nhận tất cả các thay đổi và ngừng theo dõi các bản sửa đổi. Giờ đây, bạn có thể áp dụng kiến thức này để quản lý hiệu quả các bản sửa đổi trong tài liệu Word của riêng mình bằng Aspose.Words for .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để bật tính năng theo dõi sửa đổi trong Aspose.Words cho .NET?

#### Giải pháp 1:

 Trả lời: Để bật theo dõi sửa đổi trong Aspose.Words cho .NET, hãy sử dụng`StartTrackRevisions` phương pháp của`Document` đối tượng và chỉ định tên tác giả cũng như ngày bắt đầu theo dõi sửa đổi.

```csharp
doc.StartTrackRevisions("John Doe", DateTime.Now);
```

#### Giải pháp 2:

 Đáp: Bạn cũng có thể kích hoạt tính năng theo dõi sửa đổi bằng cách sử dụng`Document` hàm tạo chấp nhận`trackRevisions`Và`author` thông số.

```csharp
Document doc = new Document("document.docx", new LoadOptions { TrackRevisions = true, Author = "John Doe" });
```

#### Câu hỏi: Làm cách nào để chấp nhận tất cả các thay đổi trong tài liệu bằng Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`AcceptAllRevisions` phương pháp của`Document` phản đối việc chấp nhận mọi thay đổi được thực hiện đối với tài liệu.

```csharp
doc.AcceptAllRevisions();
```

#### Hỏi: Làm cách nào để lưu tài liệu đã sửa đổi với các bản sửa đổi được chấp nhận?

 Sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu đã sửa đổi với các bản sửa đổi được chấp nhận. Đảm bảo cung cấp đường dẫn tệp chính xác.

```csharp
doc.Save("path/to/the/document.docx");
```

#### Câu hỏi: Làm cách nào để ngừng theo dõi các bản sửa đổi trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`StopTrackRevisions` phương pháp của`Document` phản đối việc ngừng theo dõi các phiên bản.

```csharp
doc.StopTrackRevisions();
```

#### Câu hỏi: Làm cách nào để xóa đoạn đã sửa đổi trong tài liệu bằng Aspose.Words cho .NET?

 Đáp: Để xóa đoạn văn đã sửa đổi trong tài liệu, bạn có thể sử dụng`Remove` phương pháp thu thập đoạn văn.

```csharp
ParagraphCollection paragraphs = body.Paragraphs;
Paragraph para = paragraphs[2];
para.Remove();
```