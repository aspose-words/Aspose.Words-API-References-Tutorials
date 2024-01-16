---
title: Xóa nhận xét trong tệp PDF
linktitle: Xóa nhận xét trong tệp PDF
second_title: API xử lý tài liệu Aspose.Words
description: Xóa nhận xét trong tệp PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/remove-comments-in-pdf/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách xóa nhận xét trong tệp PDF bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tải tài liệu

Bước đầu tiên là tải tài liệu chứa các nhận xét.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## Bước 2: Ẩn nhận xét trong PDF

Chúng tôi sẽ định cấu hình tùy chọn bố cục để ẩn nhận xét khi tạo tệp PDF.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## Bước 3: Lưu tài liệu dưới dạng PDF

Cuối cùng chúng ta sẽ lưu tài liệu ở định dạng PDF bằng cách xóa bình luận.

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Định dạng đầu ra đánh dấu

Đầu ra có thể được định dạng trong markdown để cải thiện khả năng đọc. Ví dụ :

```markdown
- Comments are hidden in the generated PDF.
```

### Mã nguồn ví dụ cho Xóa nhận xét trong Pdf bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để xóa nhận xét trong tệp PDF bằng Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

// Ẩn nhận xét trong PDF.
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã tìm hiểu cách xóa nhận xét khỏi tệp PDF bằng Aspose.Words cho .NET. Bằng cách sử dụng các tùy chọn bố cục thích hợp, chúng tôi có thể ẩn nhận xét khi tạo tệp PDF. Aspose.Words for .NET cung cấp tính linh hoạt cao để thao tác với các tệp Word và chuyển đổi chúng sang các định dạng khác nhau, bao gồm cả PDF. Bây giờ bạn có thể áp dụng kiến thức này để xóa nhận xét trong tệp PDF của riêng mình bằng Aspose.Words for .NET.

### Câu hỏi thường gặp về xóa nhận xét trong tệp pdf

#### Hỏi: Làm cách nào để tải lên tài liệu trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Document` lớp Aspose.Words dành cho .NET để tải tài liệu từ một tệp. Bạn có thể chỉ định đường dẫn tài liệu đầy đủ.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Hỏi: Làm cách nào để ẩn nhận xét trong tệp PDF được tạo bằng Aspose.Words dành cho .NET?

 Đáp: Hãy sử dụng`CommentDisplayMode` tài sản của`LayoutOptions` đối tượng để định cấu hình cách hiển thị nhận xét khi tạo tệp PDF. Để ẩn nhận xét, hãy đặt thuộc tính này thành`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### Hỏi: Làm cách nào để lưu tài liệu dưới dạng PDF bằng Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu ở định dạng PDF. Chỉ định đường dẫn đầy đủ của tệp PDF.

```csharp
doc.Save("path/to/the/file.pdf");
```