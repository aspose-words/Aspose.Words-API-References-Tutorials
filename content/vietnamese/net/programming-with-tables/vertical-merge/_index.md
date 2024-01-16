---
title: Hợp nhất theo chiều dọc
linktitle: Hợp nhất theo chiều dọc
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hợp nhất các ô theo chiều dọc trong bảng trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/vertical-merge/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách hợp nhất các ô theo chiều dọc trong bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể Hợp nhất dọc các ô trong bảng của mình trong tài liệu Word.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tải tài liệu
Để bắt đầu Xử lý văn bản với tài liệu, hãy làm theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo một tài liệu mới
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Hợp nhất các ô theo chiều dọc
Tiếp theo chúng ta sẽ gộp các ô theo chiều dọc trong bảng. Sử dụng mã sau đây:

```csharp
// Chèn một ô
builder. InsertCell();

// Áp dụng phối dọc cho ô đầu tiên
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Chèn một ô khác
builder. InsertCell();

// Không áp dụng hợp nhất theo chiều dọc cho ô
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Chèn một ô
builder. InsertCell();

// Áp dụng phối dọc với ô trước đó
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Chèn một ô khác
builder. InsertCell();

// Không áp dụng hợp nhất theo chiều dọc cho ô
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Kết thúc việc tạo bảng
builder. EndTable();
```

Trong mã này, chúng tôi sử dụng hàm tạo DocumentBuilder để chèn các ô vào bảng. Chúng tôi áp dụng tính năng hợp nhất theo chiều dọc cho các ô bằng thuộc tính CellFormat.VerticalMerge. Chúng tôi sử dụng CellMerge.First để hợp nhất ô đầu tiên, CellMerge.Previous để hợp nhất với ô trước đó và CellMerge.None để không hợp nhất theo chiều dọc.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi cùng với các ô đã hợp nhất. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Hợp nhất dọc bằng Aspose.Words cho .NET 
```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Ô này được hợp nhất theo chiều dọc với ô ở trên và phải trống.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách hợp nhất các ô theo chiều dọc trong một bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể dễ dàng hợp nhất các ô Dọc trong bảng của mình.