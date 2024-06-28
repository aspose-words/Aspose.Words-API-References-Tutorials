---
title: Tạo Bookmark Trong Tài Liệu Word
linktitle: Tạo Bookmark Trong Tài Liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo dấu trang trong tài liệu word và chỉ định mức xem trước dấu trang trong tệp PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-bookmarks/create-bookmark/
---

Trong bài viết này, chúng ta sẽ khám phá mã nguồn C# ở trên để hiểu cách sử dụng hàm Tạo dấu trang trong thư viện Aspose.Words cho .NET. Tính năng này cho phép bạn tạo dấu trang trong tài liệu và chỉ định mức xem trước dấu trang trong tệp PDF đầu ra.

## Điều kiện tiên quyết

- Kiến thức cơ bản về ngôn ngữ C#.
- Môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

## Bước 1: Tạo tài liệu và trình tạo

 Trước khi tạo dấu trang, chúng ta cần tạo một tài liệu và trình tạo tài liệu bằng cách sử dụng`Document` Và`DocumentBuilder` các đối tượng:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Tạo bookmark chính

 Chúng tôi sử dụng`StartBookmark` phương pháp để bắt đầu một dấu trang chính và`EndBookmark` phương pháp để kết thúc nó. Ở giữa, chúng ta có thể thêm văn bản và các dấu trang khác:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Thêm nhiều dấu trang hoặc văn bản ở đây.

builder. EndBookmark("My Bookmark");
```

## Bước 3: Tạo dấu trang lồng nhau

 Chúng ta cũng có thể tạo các dấu trang lồng nhau bên trong dấu trang chính. Chúng tôi sử dụng tương tự`StartBookmark` Và`EndBookmark` phương pháp tạo và kết thúc dấu trang lồng nhau:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Bước 4: Chỉ định mức xem trước dấu trang trong tệp PDF đầu ra

 Chúng tôi sử dụng`PdfSaveOptions` đối tượng để chỉ định mức xem trước dấu trang trong tệp PDF đầu ra. Chúng tôi sử dụng`BookmarksOutlineLevels` tài sản

  để thêm dấu trang chính và dấu trang lồng nhau với cấp độ tương ứng:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Mã nguồn mẫu cho Tạo dấu trang bằng Aspose.Words cho .NET

Đây là mã nguồn ví dụ đầy đủ để minh họa việc tạo dấu trang bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Phần kết luận

Trong bài viết này, chúng ta đã khám phá mã nguồn C# để hiểu cách sử dụng chức năng Tạo dấu trang của Aspose.Words cho .NET. Chúng tôi đã làm theo hướng dẫn từng bước để tạo dấu trang trong tài liệu và chỉ định mức xem trước dấu trang trong tệp PDF đầu ra.

### Câu hỏi thường gặp

#### Câu hỏi: Điều kiện tiên quyết để sử dụng chức năng "Tạo dấu trang" trong Aspose.Words cho .NET là gì?

Đáp: Để sử dụng chức năng "Tạo dấu trang" trong Aspose.Words cho .NET, bạn phải có kiến thức cơ bản về ngôn ngữ C#. Bạn cũng cần có môi trường phát triển .NET có cài đặt thư viện Aspose.Words.

#### Hỏi: Làm cách nào để tạo tài liệu trong Aspose.Words cho .NET?

 Trả lời: Để tạo tài liệu trong Aspose.Words cho .NET, bạn có thể sử dụng`Document` lớp học. Đây là một mã mẫu:

```csharp
Document doc = new Document();
```

#### Câu hỏi: Làm cách nào để tạo dấu trang chính trong tài liệu bằng Aspose.Words cho .NET?

 Trả lời: Để tạo dấu trang chính trong tài liệu bằng Aspose.Words cho .NET, bạn có thể sử dụng`StartBookmark` phương pháp để bắt đầu đánh dấu trang, thêm văn bản hoặc các dấu trang khác vào bên trong, sau đó sử dụng` EndBookmark` để kết thúc nó. Đây là một mã mẫu:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Câu hỏi: Làm cách nào để tạo dấu trang lồng nhau bên trong dấu trang chính bằng Aspose.Words cho .NET?

 Trả lời: Để tạo dấu trang lồng nhau bên trong dấu trang chính bằng Aspose.Words cho .NET, bạn có thể sử dụng tương tự`StartBookmark` Và`EndBookmark` phương pháp bắt đầu và kết thúc dấu trang lồng nhau. Đây là một mã mẫu:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Câu hỏi: Làm cách nào để chỉ định mức xem trước dấu trang trong tệp PDF đầu ra bằng Aspose.Words cho .NET?

 Trả lời: Để chỉ định mức xem trước dấu trang trong tệp PDF đầu ra bằng Aspose.Words cho .NET, bạn có thể sử dụng`PdfSaveOptions` lớp học và`BookmarksOutlineLevels` tài sản. Bạn có thể thêm dấu trang chính và dấu trang lồng nhau với cấp độ tương ứng. Đây là một mã mẫu:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Hỏi: Làm cách nào để lưu tài liệu sau khi tạo dấu trang bằng Aspose.Words cho .NET?

 Trả lời: Để lưu tài liệu sau khi tạo dấu trang bằng Aspose.Words cho .NET, bạn có thể sử dụng`Save` phương pháp của`Document` đối tượng chỉ định đường dẫn tệp đích. Đây là một mã mẫu:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Câu hỏi: Làm cách nào để chỉ định mức xem trước dấu trang trong tệp PDF đầu ra bằng Aspose.Words cho .NET?

 Trả lời: Để chỉ định mức xem trước dấu trang trong tệp PDF đầu ra bằng Aspose.Words cho .NET, bạn có thể sử dụng`PdfSaveOptions` lớp học và`BookmarksOutlineLevels` tài sản. Bạn có thể thêm dấu trang chính và dấu trang lồng nhau với cấp độ tương ứng. Đây là một mã mẫu:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Câu hỏi: Làm cách nào để tạo dấu trang lồng nhau bên trong dấu trang chính bằng Aspose.Words cho .NET?

 Trả lời: Để tạo các dấu trang lồng nhau bên trong dấu trang chính bằng Aspose.Words cho .NET, bạn có thể sử dụng tương tự`StartBookmark` Và`EndBookmark` phương pháp bắt đầu và kết thúc các dấu trang lồng nhau. Đảm bảo chỉ định dấu trang gốc làm tham số khi gọi`StartBookmark` phương pháp. Đây là một mã mẫu:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Hỏi: Làm cách nào để thêm văn bản vào dấu trang bằng Aspose.Words cho .NET?

 Trả lời: Để thêm văn bản bên trong dấu trang bằng Aspose.Words cho .NET, bạn có thể sử dụng`Write` phương pháp của`DocumentBuilder`đối tượng chỉ định văn bản cần thêm. Đây là một mã mẫu:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Câu hỏi: Làm cách nào để tạo dấu trang chính trong tài liệu bằng Aspose.Words cho .NET?

 Trả lời: Để tạo dấu trang chính trong tài liệu bằng Aspose.Words cho .NET, bạn có thể sử dụng`StartBookmark` phương pháp để bắt đầu đánh dấu và`EndBookmark` phương pháp để kết thúc nó. Đây là một mã mẫu:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```