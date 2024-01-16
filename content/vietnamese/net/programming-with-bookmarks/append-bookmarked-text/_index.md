---
title: Nối văn bản đã đánh dấu vào tài liệu Word
linktitle: Nối văn bản đã đánh dấu vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm văn bản từ dấu trang trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/append-bookmarked-text/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng chức năng Nối văn bản được đánh dấu trong thư viện Aspose.Words cho .NET. Tính năng này cho phép bạn thêm văn bản có trong một dấu trang cụ thể của tài liệu Word vào tài liệu khác.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Lấy đoạn văn từ dấu trang

 Trước khi bắt đầu thêm văn bản đánh dấu, chúng ta cần lấy các đoạn văn chứa phần đầu và phần cuối của dấu trang. Điều này có thể được thực hiện bằng cách truy cập vào`BookmarkStart` Và`BookmarkEnd` Thuộc tính của dấu trang:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Bước 2: Kiểm tra đoạn văn gốc

Chúng tôi kiểm tra xem đoạn văn bắt đầu và kết thúc có cha mẹ hợp lệ hay không, nghĩa là chúng có thực sự thuộc về một đoạn văn hay không. Nếu không, chúng tôi sẽ tạo ra một ngoại lệ:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Bước 3: Kiểm tra phần cha của đoạn văn

Chúng tôi kiểm tra xem đoạn đầu và đoạn cuối có cùng phần gốc hay không. Nếu không, điều đó có nghĩa là các đoạn văn không nằm trong cùng một phần hoặc tài liệu và chúng tôi sẽ đưa ra một ngoại lệ:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Bước 4: Sao chép đoạn văn

Chúng ta lặp qua các nút (đoạn) từ đoạn đầu đến đoạn cuối. Đối với mỗi nút, chúng tôi tạo một bản sao và nhập nó vào ngữ cảnh của tài liệu đích:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Mã nguồn mẫu cho Nối văn bản được đánh dấu bằng Aspose.Words cho .NET

Đây là mã nguồn ví dụ đầy đủ để minh họa việc thêm văn bản từ dấu trang bằng Aspose.Words cho .NET:

```csharp

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

```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng chức năng Nối văn bản được đánh dấu của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để lấy các đoạn văn từ dấu trang, xác minh cha mẹ và sao chép các đoạn văn sang tài liệu khác.

### Câu hỏi thường gặp về nối văn bản đã đánh dấu vào tài liệu word

#### Câu hỏi 1: Điều kiện tiên quyết để sử dụng tính năng "Thêm văn bản có dấu trang" trong Aspose.Words cho .NET là gì?

Trả lời: Để sử dụng chức năng "Thêm văn bản có dấu trang" trong Aspose.Words cho .NET, bạn cần có kiến thức cơ bản về ngôn ngữ C#. Bạn cũng cần có môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

#### Câu hỏi 2: Làm cách nào để lấy các đoạn văn có phần đầu và phần cuối của dấu trang trong tài liệu Word?

Đáp: Để lấy các đoạn chứa phần đầu và phần cuối của dấu trang trong tài liệu Word, bạn có thể truy cập vào`BookmarkStart` Và`BookmarkEnd` thuộc tính của dấu trang. Đây là một mã mẫu:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Câu hỏi 3: Điều gì xảy ra nếu đoạn đầu và đoạn cuối không có phần cha hợp lệ?

Trả lời: Nếu đoạn đầu và đoạn cuối không có phần cha hợp lệ, tức là chúng không thực sự là đoạn văn, thì một ngoại lệ sẽ được đưa ra. Tình trạng này không thể được quản lý vào lúc này.
