---
title: Hiển thị ẩn nội dung được đánh dấu trong tài liệu Word
linktitle: Hiển thị ẩn nội dung được đánh dấu trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hiển thị hoặc ẩn nội dung dấu trang trong tài liệu word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng chức năng Hiển thị ẩn nội dung được đánh dấu trong thư viện Aspose.Words cho .NET. Tính năng này cho phép bạn hiển thị hoặc ẩn nội dung của dấu trang trong tài liệu word dựa trên một điều kiện cụ thể khi hợp nhất dữ liệu.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Lấy dấu trang

 Chúng tôi sử dụng`Bookmarks` thuộc tính của phạm vi tài liệu để lấy dấu trang cụ thể mà chúng tôi muốn hiển thị hoặc ẩn nội dung:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Bước 2: Chèn các trường hợp nhất

 Chúng tôi sử dụng trình tạo tài liệu`DocumentBuilder` để chèn các trường hợp nhất cần thiết. Các trường hợp nhất này sẽ đặt điều kiện hiển thị hoặc ẩn nội dung dấu trang tùy thuộc vào giá trị của`showHide` Biến đổi:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Bước 3: Di chuyển nội dung bookmark

Chúng tôi lặp qua nội dung của dấu trang và di chuyển nó để nó xuất hiện

isse trước dấu trang. Điều này sẽ kiểm soát việc hiển thị hoặc ẩn nội dung dựa trên điều kiện đã chỉ định:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Bước 4: Di chuyển phần nội dung còn lại của bookmark

Chúng ta di chuyển phần còn lại của nội dung bookmark sau bookmark, sử dụng nút cuối của bookmark làm điểm chèn:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Bước 5: Thực hiện việc ghép

 Chúng tôi sử dụng`Execute` phương pháp tài liệu`s `Mail Merge` object to execute the merge using the bookmark name and the value of the `biến showHide`:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Mã nguồn ví dụ cho Hiển thị Ẩn nội dung được đánh dấu bằng Aspose.Words cho .NET

Dưới đây là ví dụ đầy đủ về Mã nguồn để minh họa việc hiển thị hoặc ẩn nội dung dấu trang bằng Aspose.Words cho .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{Dấu trang MERGEFIELD}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng tính năng Hiển thị ẩn nội dung được đánh dấu của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để hiển thị hoặc ẩn nội dung của dấu trang dựa trên điều kiện cụ thể khi hợp nhất dữ liệu.

### Câu hỏi thường gặp về ẩn nội dung được đánh dấu trong tài liệu word

#### Hỏi: Tôi có thể sử dụng cùng một điều kiện cho nhiều dấu trang trong cùng một tài liệu không?

Đáp: Có, bạn có thể sử dụng cùng một điều kiện cho nhiều dấu trang trong cùng một tài liệu. Chỉ cần lặp lại các bước 2-5 cho mỗi dấu trang, điều chỉnh tên dấu trang và giá trị tùy ý của dấu trang.`showhide` biến khi cần thiết.

#### Hỏi: Làm cách nào tôi có thể thêm nhiều điều kiện hơn để hiển thị hoặc ẩn nội dung dấu trang?

 Đáp: Để thêm nhiều điều kiện hơn, bạn có thể sử dụng các toán tử logic như`AND` Và`OR` trong mã để chèn các trường hợp nhất ở bước 2. Chỉnh sửa điều kiện trong mã sau để thêm các điều kiện bổ sung:

```csharp
builder. Write("\" = \"true\" ");
```

#### Hỏi: Làm cách nào tôi có thể xóa dấu trang trong tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để xóa dấu trang trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng`Remove` phương pháp từ`Bookmarks` tập hợp phạm vi tài liệu. Đây là mã mẫu để xóa một dấu trang cụ thể:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Câu hỏi: Thư viện Aspose.Words có miễn phí không?

 Trả lời: Thư viện Aspose.Words là thư viện thương mại và cần có giấy phép hợp lệ để sử dụng trong các dự án của bạn. Anh có thể kiểm tra[Aspose.Words cho tài liệu tham khảo API .NET](https://reference.aspose.com/words/net/) để tìm hiểu thêm về các tùy chọn cấp phép và giá cả.

#### Câu hỏi: Có thư viện nào khác dành cho Xử lý văn bản với tài liệu Word trong .NET không?

Đáp: Có, có các thư viện khác dành cho Xử lý văn bản với tài liệu Word trong .NET, chẳng hạn như Open XML SDK và GemBox.Document. Bạn có thể khám phá những thư viện này dưới dạng các lựa chọn thay thế cho Aspose.Words dựa trên nhu cầu và sở thích cụ thể của bạn.