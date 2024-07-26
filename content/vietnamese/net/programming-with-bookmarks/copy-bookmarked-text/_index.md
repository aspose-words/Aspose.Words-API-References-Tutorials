---
title: Sao chép văn bản được đánh dấu trong tài liệu Word
linktitle: Sao chép văn bản được đánh dấu trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Dễ dàng sao chép văn bản được đánh dấu giữa các tài liệu Word bằng Aspose.Words cho .NET. Tìm hiểu cách thực hiện với hướng dẫn từng bước này.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/copy-bookmarked-text/
---
## Giới thiệu

Bạn có bao giờ thấy mình cần sao chép các phần cụ thể từ tài liệu Word này sang tài liệu Word khác không? Vâng, bạn thật may mắn! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách sao chép văn bản được đánh dấu từ tài liệu Word này sang tài liệu Word khác bằng Aspose.Words cho .NET. Cho dù bạn đang tạo báo cáo động hay tự động tạo tài liệu, hướng dẫn này sẽ đơn giản hóa quy trình cho bạn.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào, hãy đảm bảo bạn có những điều sau:

-  Thư viện Aspose.Words for .NET: Bạn có thể tải xuống từ[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ môi trường phát triển .NET nào khác.
- Kiến thức cơ bản về C#: Làm quen với lập trình C# và .NET framework.

## Nhập không gian tên

Để bắt đầu, hãy đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án của mình:

```csharp
using Aspose.Words;
using Aspose.Words.Import;
using Aspose.Words.Bookmark;
```

## Bước 1: Tải tài liệu nguồn

Trước tiên, bạn cần tải tài liệu nguồn chứa văn bản đã đánh dấu mà bạn muốn sao chép.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

 Đây,`dataDir` là đường dẫn đến thư mục tài liệu của bạn và`Bookmarks.docx` là tài liệu nguồn.

## Bước 2: Xác định dấu trang

Tiếp theo, xác định dấu trang bạn muốn sao chép từ tài liệu nguồn.

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

 Thay thế`"MyBookmark1"` với tên thật của dấu trang của bạn.

## Bước 3: Tạo tài liệu đích

Bây giờ, tạo một tài liệu mới nơi văn bản được đánh dấu sẽ được sao chép.

```csharp
Document dstDoc = new Document();
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Bước 4: Nhập nội dung được đánh dấu

 Để đảm bảo kiểu dáng và định dạng được giữ nguyên, hãy sử dụng`NodeImporter` để nhập nội dung được đánh dấu từ tài liệu nguồn sang tài liệu đích.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(importer, srcBookmark, dstNode);
```

## Bước 5: Xác định phương thức AppendBookmarkedText

Đây là nơi phép thuật xảy ra. Xác định phương thức xử lý việc sao chép văn bản được đánh dấu:

```csharp
private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
{
    Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;
    Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

    if (startPara == null || endPara == null)
        throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

    if (startPara.ParentNode != endPara.ParentNode)
        throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");

    Node endNode = endPara.NextSibling;

    for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
    {
        Node newNode = importer.ImportNode(curNode, true);
        dstNode.AppendChild(newNode);
    }
}
```

## Bước 6: Lưu tài liệu đích

Cuối cùng, lưu tài liệu đích để xác minh nội dung đã sao chép.

```csharp
dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Phần kết luận

Và thế là xong! Bạn đã sao chép thành công văn bản được đánh dấu từ tài liệu Word này sang tài liệu Word khác bằng Aspose.Words for .NET. Phương pháp này rất hiệu quả để tự động hóa các tác vụ thao tác tài liệu, giúp quy trình làm việc của bạn hiệu quả và hợp lý hơn.

## Câu hỏi thường gặp

### Tôi có thể sao chép nhiều dấu trang cùng một lúc không?
Có, bạn có thể lặp qua nhiều dấu trang và sử dụng cùng một phương pháp để sao chép từng dấu trang.

### Điều gì xảy ra nếu không tìm thấy dấu trang?
 Các`Range.Bookmarks` tài sản sẽ trở lại`null`, vì vậy hãy đảm bảo bạn xử lý trường hợp này để tránh trường hợp ngoại lệ.

### Tôi có thể giữ nguyên định dạng của dấu trang gốc không?
 Tuyệt đối! sử dụng`ImportFormatMode.KeepSourceFormatting` đảm bảo rằng định dạng ban đầu được giữ nguyên.

### Có giới hạn về kích thước của văn bản được đánh dấu không?
Không có giới hạn cụ thể nhưng hiệu suất có thể khác nhau đối với các tài liệu cực lớn.

### Tôi có thể sao chép văn bản giữa các định dạng tài liệu Word khác nhau không?
Có, Aspose.Words hỗ trợ nhiều định dạng Word khác nhau và phương pháp này hoạt động trên các định dạng này.