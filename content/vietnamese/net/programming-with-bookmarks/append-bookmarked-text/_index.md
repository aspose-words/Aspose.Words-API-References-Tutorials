---
title: Nối văn bản đã đánh dấu vào tài liệu Word
linktitle: Nối văn bản đã đánh dấu vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm văn bản được đánh dấu vào tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước này. Hoàn hảo cho các nhà phát triển.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/append-bookmarked-text/
---
## Giới thiệu

Này! Bạn đã bao giờ thử nối thêm văn bản từ một phần được đánh dấu trong tài liệu Word và thấy việc này phức tạp chưa? Bạn may mắn! Hướng dẫn này sẽ hướng dẫn bạn qua quy trình sử dụng Aspose.Words cho .NET. Chúng tôi sẽ chia nó thành các bước đơn giản để bạn có thể dễ dàng làm theo. Hãy cùng bắt tay vào và thêm văn bản được đánh dấu đó vào như một người chuyên nghiệp!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có mọi thứ bạn cần:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt nó. Nếu không, bạn có thể[tải về tại đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Bất kỳ môi trường phát triển .NET nào như Visual Studio.
- Kiến thức cơ bản về C#: Hiểu các khái niệm lập trình C# cơ bản sẽ giúp ích.
- Tài liệu Word có dấu trang: Một tài liệu Word có dấu trang được thiết lập mà chúng tôi sẽ sử dụng để nối văn bản từ đó.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Điều này sẽ đảm bảo chúng ta có tất cả các công cụ cần thiết trong tầm tay.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Importing;
```

Hãy chia nhỏ ví dụ thành các bước chi tiết.

## Bước 1: Tải tài liệu và khởi tạo các biến

Được rồi, hãy bắt đầu bằng cách tải tài liệu Word của chúng ta và khởi tạo các biến mà chúng ta cần.

```csharp
// Tải tài liệu nguồn và đích.
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");

// Khởi tạo trình nhập tài liệu.
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

// Tìm dấu trang trong tài liệu nguồn.
Bookmark srcBookmark = srcDoc.Range.Bookmarks["YourBookmarkName"];
```

## Bước 2: Xác định đoạn bắt đầu và kết thúc

Bây giờ, hãy xác định vị trí các đoạn văn nơi dấu trang bắt đầu và kết thúc. Điều này rất quan trọng vì chúng ta cần xử lý văn bản trong các giới hạn này.

```csharp
// Đây là đoạn chứa phần đầu của dấu trang.
Paragraph startPara = (Paragraph)srcBookmark.BookmarkStart.ParentNode;

// Đây là đoạn chứa phần cuối của dấu trang.
Paragraph endPara = (Paragraph)srcBookmark.BookmarkEnd.ParentNode;

if (startPara == null || endPara == null)
    throw new InvalidOperationException("Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
```

## Bước 3: Xác thực đoạn văn gốc

Chúng ta cần đảm bảo đoạn đầu và đoạn cuối có cùng phần gốc. Đây là một kịch bản đơn giản để giữ cho mọi thứ đơn giản.

```csharp
// Hãy giới hạn bản thân trong một kịch bản khá đơn giản.
if (startPara.ParentNode != endPara.ParentNode)
    throw new InvalidOperationException("Start and end paragraphs have different parents, cannot handle this scenario yet.");
```

## Bước 4: Xác định nút dừng

Tiếp theo, chúng ta cần xác định nút nơi chúng ta sẽ dừng sao chép văn bản. Đây sẽ là nút ngay sau đoạn kết thúc.

```csharp
// Chúng tôi muốn sao chép tất cả các đoạn từ đoạn đầu đến (và bao gồm) đoạn cuối,
// do đó nút mà chúng ta dừng lại là nút sau đoạn kết thúc.
Node endNode = endPara.NextSibling;
```

## Bước 5: Nối văn bản đã đánh dấu vào tài liệu đích

Cuối cùng, hãy lặp qua các nút từ đoạn bắt đầu đến nút sau đoạn kết thúc và nối chúng vào tài liệu đích.

```csharp
for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
    // Điều này tạo ra một bản sao của nút hiện tại và nhập nó (làm cho nó hợp lệ) trong ngữ cảnh
    // của tài liệu đích. Nhập có nghĩa là điều chỉnh kiểu và liệt kê số nhận dạng một cách chính xác.
    Node newNode = importer.ImportNode(curNode, true);

    // Nối nút đã nhập vào tài liệu đích.
    dstDoc.FirstSection.Body.AppendChild(newNode);
}

// Lưu tài liệu đích với văn bản được nối thêm.
dstDoc.Save("appended_document.docx");
```

## Phần kết luận

Và bạn có nó rồi đấy! Bạn đã nối thành công văn bản từ phần được đánh dấu trong tài liệu Word bằng Aspose.Words for .NET. Công cụ mạnh mẽ này giúp việc thao tác tài liệu trở nên dễ dàng và giờ đây bạn đã có thêm một thủ thuật nữa. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Tôi có thể thêm văn bản từ nhiều dấu trang cùng một lúc không?
Có, bạn có thể lặp lại quy trình cho từng dấu trang và nối thêm văn bản tương ứng.

### Điều gì sẽ xảy ra nếu đoạn đầu và đoạn cuối có phần gốc khác nhau?
Ví dụ hiện tại giả định rằng chúng có cùng cha mẹ. Đối với các bậc cha mẹ khác nhau, cần phải xử lý phức tạp hơn.

### Tôi có thể giữ nguyên định dạng ban đầu của văn bản được thêm vào không?
 Tuyệt đối! Các`ImportFormatMode.KeepSourceFormatting` đảm bảo định dạng ban đầu được giữ nguyên.

### Có thể nối văn bản vào một vị trí cụ thể trong tài liệu đích không?
Có, bạn có thể nối văn bản vào bất kỳ vị trí nào bằng cách điều hướng đến nút mong muốn trong tài liệu đích.

### Điều gì sẽ xảy ra nếu tôi cần thêm văn bản từ dấu trang vào phần mới?
Bạn có thể tạo một phần mới trong tài liệu đích và nối văn bản vào đó.