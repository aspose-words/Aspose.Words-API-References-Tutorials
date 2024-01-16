---
title: Đánh dấu cột bảng trong tài liệu Word
linktitle: Đánh dấu cột bảng trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đánh dấu cột trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/bookmark-table-columns/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng hàm Cột bảng đánh dấu trong thư viện Aspose.Words cho .NET. Tính năng này cho phép bạn đánh dấu một cột cụ thể của bảng trong tài liệu Word và truy cập nội dung của cột đó.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Tạo bảng

 Trước khi tạo dấu trang trên một cột trong bảng, trước tiên chúng ta phải tạo bảng bằng cách sử dụng`DocumentBuilder`sự vật. Trong ví dụ của chúng tôi, chúng tôi tạo một bảng có hai hàng và hai cột:

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## Bước 2: Tạo dấu trang cột

 Chúng tôi sử dụng`StartBookmark` phương pháp tạo dấu trang trên một cột cụ thể của bảng. Trong ví dụ của chúng tôi, chúng tôi sử dụng tên "MyBookmark" cho dấu trang:

```csharp
builder. StartBookmark("MyBookmark");
```

## Bước 3: Truy cập nội dung cột

 Chúng tôi xem qua tất cả các dấu trang trong tài liệu và hiển thị tên của chúng. Nếu dấu trang là một cột, chúng ta truy cập nội dung của cột đó bằng chỉ mục cột và`GetText` phương pháp:

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Mã nguồn ví dụ cho Cột bảng đánh dấu bằng Aspose.Words cho .NET

Đây là mã nguồn mẫu đầy đủ để minh họa việc tạo dấu trang trên một cột trong bảng bằng Aspose.Words cho .NET:

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng chức năng Cột bảng đánh dấu của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để đánh dấu một cột cụ thể của bảng trong tài liệu Word và chuyển đến nội dung của cột đó.

### Câu hỏi thường gặp về cột bảng đánh dấu trong tài liệu word

#### Câu hỏi: Điều kiện tiên quyết để sử dụng tính năng "Dấu trang cho cột bảng" trong Aspose.Words cho .NET là gì?

Đáp: Để sử dụng tính năng "Dấu trang cho các cột trong bảng" trong Aspose.Words cho .NET, bạn cần có kiến thức cơ bản về ngôn ngữ C#. Bạn cũng cần có môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

#### Hỏi: Làm cách nào để tạo bảng có các cột trong tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để tạo bảng có các cột trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng`DocumentBuilder` đối tượng chèn ô và nội dung vào bảng. Đây là một mã mẫu:

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Câu hỏi: Làm cách nào để đánh dấu một cột trong bảng bằng Aspose.Words cho .NET?

 Trả lời: Để tạo dấu trang trên một cột trong bảng bằng Aspose.Words cho .NET, bạn có thể sử dụng`StartBookmark` phương pháp của`DocumentBuilder` đối tượng để bắt đầu đánh dấu trên một cột trong bảng cụ thể. Đây là một mã mẫu:

```csharp
builder.StartBookmark("MyBookmark");
```

#### Câu hỏi: Làm cách nào để truy cập nội dung cột trong bảng từ dấu trang bằng Aspose.Words cho .NET?

Trả lời: Để truy cập nội dung của một cột trong bảng từ dấu trang bằng Aspose.Words cho .NET, bạn có thể lặp qua tất cả dấu trang trong tài liệu, kiểm tra xem dấu trang có phải là một cột hay không và sử dụng chỉ mục của cột để truy cập nội dung của cột đó. Đây là một mã mẫu:

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             // Làm điều gì đó với nội dung của cột...
         }
     }
}
```

#### Câu hỏi: Có giới hạn về số lượng cột tôi có thể tạo trong bảng có dấu trang cột không?

Trả lời: Không có giới hạn cụ thể về số lượng cột bạn có thể tạo trong bảng có dấu trang cột bằng Aspose.Words cho .NET. Giới hạn chủ yếu phụ thuộc vào tài nguyên có sẵn trên hệ thống của bạn và thông số kỹ thuật của định dạng tệp Word bạn đang sử dụng. Tuy nhiên, không nên tạo số lượng cột quá lớn vì điều này có thể ảnh hưởng đến hiệu suất và khả năng đọc của tài liệu cuối cùng.