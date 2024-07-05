---
title: Sao chép văn bản được đánh dấu trong tài liệu Word
linktitle: Sao chép văn bản được đánh dấu trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sao chép văn bản dấu trang trong tài liệu word sang tài liệu khác bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/copy-bookmarked-text/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng chức năng Sao chép văn bản được đánh dấu trong thư viện Aspose.Words cho .NET. Tính năng này cho phép bạn sao chép nội dung của một dấu trang cụ thể từ tài liệu nguồn này sang tài liệu khác.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Tải tài liệu nguồn

 Trước khi sao chép văn bản đánh dấu, chúng ta cần tải tài liệu nguồn vào một`Document` đối tượng sử dụng đường dẫn tệp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Bookmarks.docx");
```

## Bước 2: Lấy dấu trang nguồn

 Chúng tôi sử dụng`Bookmarks` thuộc tính của phạm vi tài liệu nguồn để lấy dấu trang cụ thể mà chúng tôi muốn sao chép:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];
```

## Bước 3: Tạo tài liệu đích

Chúng tôi tạo một tài liệu mới sẽ đóng vai trò là tài liệu đích để sao chép nội dung dấu trang:

```csharp
Document dstDoc = new Document();
```

## Bước 4: Chỉ định vị trí sao chép

Chúng tôi chỉ định vị trí mà chúng tôi muốn thêm văn bản đã sao chép. Trong ví dụ của chúng tôi, chúng tôi thêm văn bản vào cuối phần nội dung của phần cuối cùng của tài liệu đích:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

## Bước 5: Nhập và sao chép văn bản dấu trang

 Chúng tôi sử dụng một`NodeImporter`đối tượng nhập và sao chép văn bản đánh dấu từ tài liệu nguồn sang tài liệu đích:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

AppendBookmarkedText(import, srcBookmark, dstNode);

dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

### Mã nguồn mẫu cho Sao chép văn bản được đánh dấu bằng Aspose.Words cho .NET

Đây là mã nguồn ví dụ đầy đủ để minh họa việc sao chép văn bản từ dấu trang bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document srcDoc = new Document(dataDir + "Bookmarks.docx");

	// Đây là dấu trang có nội dung chúng tôi muốn sao chép.
	Bookmark srcBookmark = srcDoc.Range.Bookmarks["MyBookmark1"];

	// Chúng tôi sẽ thêm vào tài liệu này.
	Document dstDoc = new Document();

	// Giả sử chúng ta sẽ được thêm vào phần cuối của phần cuối cùng.
	CompositeNode dstNode = dstDoc.LastSection.Body;

	// Nếu bạn nhập nhiều lần mà không có một ngữ cảnh nào thì sẽ tạo ra nhiều kiểu.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);

	AppendBookmarkedText(importer, srcBookmark, dstNode);
	
	dstDoc.Save(dataDir + "WorkingWithBookmarks.CopyBookmarkedText.docx");

```

#### Nối thêm Mã nguồn văn bản được đánh dấu

```csharp

private void AppendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode)
        {
            // Đây là đoạn chứa phần đầu của dấu trang.
            Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

            // Đây là đoạn chứa phần cuối của dấu trang.
            Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

            if (startPara == null || endPara == null)
                throw new InvalidOperationException(
                    "Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

            // Hãy giới hạn bản thân trong một kịch bản khá đơn giản.
            if (startPara.ParentNode != endPara.ParentNode)
                throw new InvalidOperationException(
                    "Start and end paragraphs have different parents, cannot handle this scenario yet.");

            // Chúng tôi muốn sao chép tất cả các đoạn từ đoạn đầu đến (và bao gồm) đoạn cuối,
            // do đó nút mà chúng ta dừng lại là nút sau đoạn kết thúc.
            Node endNode = endPara.NextSibling;

            for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
            {
                //Điều này tạo ra một bản sao của nút hiện tại và nhập nó (làm cho nó hợp lệ) trong ngữ cảnh
                // của tài liệu đích. Nhập có nghĩa là điều chỉnh kiểu và liệt kê số nhận dạng một cách chính xác.
                Node newNode = importer.ImportNode(curNode, true);

                dstNode.AppendChild(newNode);
            }
        }

```
## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng hàm Sao chép văn bản được đánh dấu từ Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để sao chép nội dung của dấu trang từ tài liệu nguồn sang tài liệu khác.

### Câu hỏi thường gặp về sao chép văn bản đã đánh dấu trong tài liệu word

#### Câu hỏi: Các yêu cầu để sử dụng tính năng "Sao chép văn bản có dấu trang" trong Aspose.Words cho .NET là gì?

Đáp: Để sử dụng tính năng "Sao chép văn bản có dấu trang" trong Aspose.Words cho .NET, bạn cần có kiến thức cơ bản về ngôn ngữ C#. Bạn cũng cần có môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

#### Câu hỏi: Làm cách nào để tải tài liệu nguồn vào Aspose.Words cho .NET?

 Trả lời: Để tải tài liệu nguồn trong Aspose.Words cho .NET, bạn có thể sử dụng`Document` lớp bằng cách chỉ định đường dẫn tệp của tài liệu. Đây là một mã mẫu:

```csharp
Document srcDoc = new Document("path/to/your/document.docx");
```

#### Câu hỏi: Làm cách nào để lấy nội dung của một dấu trang cụ thể trong tài liệu nguồn bằng Aspose.Words cho .NET?

 Trả lời: Để lấy nội dung của một dấu trang cụ thể trong tài liệu nguồn bằng Aspose.Words cho .NET, bạn có thể truy cập vào`Bookmarks` thuộc tính của phạm vi tài liệu nguồn và sử dụng tên dấu trang để truy xuất dấu trang cụ thể. Đây là một mã mẫu:

```csharp
Bookmark srcBookmark = srcDoc.Range.Bookmarks["BookmarkName"];
```

#### Hỏi: Làm cách nào để chỉ định vị trí của bản sao văn bản đánh dấu trong tài liệu đích bằng Aspose.Words cho .NET?

 Trả lời: Để chỉ định nơi bạn muốn thêm văn bản đánh dấu đã sao chép trong tài liệu đích bằng Aspose.Words for .NET, bạn có thể điều hướng đến phần nội dung của phần cuối cùng của tài liệu đích. Bạn có thể dùng`LastSection` thuộc tính để truy cập phần cuối cùng và`Body` property để truy cập vào phần thân của phần đó. Đây là một mã mẫu:

```csharp
CompositeNode dstNode = dstDoc.LastSection.Body;
```

#### Câu hỏi: Làm cách nào để nhập và sao chép văn bản dấu trang từ tài liệu nguồn sang tài liệu đích bằng Aspose.Words cho .NET?

 Trả lời: Để nhập và sao chép văn bản đánh dấu từ tài liệu nguồn sang tài liệu đích bằng Aspose.Words cho .NET, bạn có thể sử dụng`NodeImporter` lớp chỉ định tài liệu nguồn, tài liệu đích và chế độ định dạng cần giữ. Sau đó bạn có thể sử dụng`AppendBookmarkedText` phương pháp thêm văn bản đánh dấu vào tài liệu đích. Đây là một mã mẫu:

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting);
AppendBookmarkedText(import, srcBookmark, dstNode);
```

#### Hỏi: Làm cách nào để lưu tài liệu đích sau khi sao chép văn bản đánh dấu bằng Aspose.Words cho .NET?

Đáp: Để lưu tài liệu đích sau khi sao chép văn bản từ dấu trang bằng Aspose.Words cho .NET, bạn có thể sử dụng`Save` phương pháp của`Document` đối tượng chỉ định đường dẫn tệp đích. Đây là một mã mẫu:

```csharp
dstDoc.Save("path/to/your/destination-document.docx");
```