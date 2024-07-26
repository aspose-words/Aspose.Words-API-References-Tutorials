---
title: Truy cập phiên bản sửa đổi
linktitle: Truy cập phiên bản sửa đổi
second_title: API xử lý tài liệu Aspose.Words
description: Truy cập phiên bản sửa đổi của tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-revisions/access-revised-version/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ chỉ cho bạn cách truy cập phiên bản sửa đổi của tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ cung cấp cho bạn mã nguồn hoàn chỉnh và chỉ cho bạn cách định dạng đầu ra đánh dấu.

## Bước 1: Tải tài liệu

Bước đầu tiên là tải lên tài liệu có chứa các bản sửa đổi.

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## Bước 2: Truy cập phiên bản đã sửa đổi

Bây giờ chúng ta sẽ chuyển sang phiên bản sửa đổi của tài liệu.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## Bước 3: Duyệt các bản sửa đổi

Tiếp theo, chúng tôi sẽ lặp qua các bản sửa đổi có trong tài liệu và hiển thị thông tin cụ thể cho các đoạn văn là mục danh sách.

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Mã nguồn mẫu cho Access Revised Version sử dụng Aspose.Words for .NET

Đây là mã nguồn hoàn chỉnh để truy cập phiên bản sửa đổi của tài liệu bằng Aspose.Words cho .NET:

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

// Chuyển sang phiên bản sửa đổi của tài liệu.
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách truy cập phiên bản sửa đổi của tài liệu Word bằng Aspose.Words cho .NET. Bằng cách tải tài liệu, điều hướng đến phiên bản đã sửa đổi và duyệt qua các bản sửa đổi, chúng tôi có thể nhận được thông tin cụ thể cho các đoạn văn là mục danh sách. Aspose.Words for .NET cung cấp các tính năng mạnh mẽ để thao tác với tài liệu Word, bao gồm quyền truy cập vào các bài đánh giá. Giờ đây, bạn có thể sử dụng kiến thức này để truy cập phiên bản sửa đổi của tài liệu Word của riêng mình bằng Aspose.Words for .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để tải tài liệu có bản sửa đổi vào Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`Document` lớp Aspose.Words dành cho .NET để tải tài liệu từ một tệp có chứa các bản sửa đổi. Bạn có thể chỉ định đường dẫn tài liệu đầy đủ.

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Câu hỏi: Làm cách nào để truy cập phiên bản sửa đổi của tài liệu trong Aspose.Words cho .NET?

 Đáp: Hãy sử dụng`RevisionsView` tài sản của`Document` đối tượng để truy cập phiên bản sửa đổi của tài liệu. Bạn có thể đặt giá trị của`RevisionsView`tài sản để`RevisionsView.Final` để hiển thị phiên bản cuối cùng mà không cần sửa đổi.

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Câu hỏi: Làm cách nào để duyệt các bản sửa đổi tài liệu trong Aspose.Words cho .NET?

Đáp: Hãy sử dụng một`foreach` vòng lặp để lặp qua các sửa đổi có trong tài liệu. Bạn có thể dùng`Revisions` tài sản của`Document` object để có được một bộ sưu tập tất cả các phiên bản của tài liệu.

```csharp
foreach (Revision revision in doc.Revisions)
{
     // Xử lý từng bản sửa đổi tại đây
}
```

#### Hỏi: Làm cách nào để kiểm tra xem một đoạn văn có phải là một mục danh sách trong Aspose.Words cho .NET không?

 Đáp: Hãy sử dụng`IsListItem` tài sản của`Paragraph` đối tượng để kiểm tra xem một đoạn văn có phải là một mục danh sách hay không. Các`IsListItem` trả lại tài sản`true` nếu đoạn văn là một mục danh sách, nếu không nó sẽ trả về`false`.

```csharp
if (paragraph.IsListItem)
{
     // Đoạn văn là một mục danh sách
}
else
{
     // Đoạn văn không phải là một mục danh sách
}
```