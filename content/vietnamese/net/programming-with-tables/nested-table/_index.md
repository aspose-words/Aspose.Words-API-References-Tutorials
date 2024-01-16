---
title: Bảng lồng nhau
linktitle: Bảng lồng nhau
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo bảng lồng nhau trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/nested-table/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách tạo bảng lồng nhau trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể tạo các bảng lồng nhau trong tài liệu Word theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tạo tài liệu và khởi tạo trình tạo tài liệu
Để bắt đầu Xử lý Từ bằng trình tạo tài liệu và tài liệu, hãy làm theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu
Document doc = new Document();

// Khởi tạo trình tạo tài liệu
DocumentBuilder builder = new DocumentBuilder(doc);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Xây dựng bảng lồng nhau
Tiếp theo, chúng ta sẽ xây dựng bảng lồng nhau bằng cách chèn các ô vào bảng bên ngoài và tạo một bảng mới bên trong ô đầu tiên. Sử dụng mã sau đây:

```csharp
// Chèn ô đầu tiên của bảng bên ngoài
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Chèn ô thứ hai của bảng bên ngoài
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Chấm dứt bảng bên ngoài
builder. EndTable();

// Di chuyển đến ô đầu tiên của bảng bên ngoài
builder.MoveTo(cell.FirstParagraph);

// Xây dựng bảng bên trong
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Cuối bảng bên trong
builder. EndTable();
```

Ở đây chúng tôi sử dụng trình tạo tài liệu để chèn các ô và nội dung vào bảng bên ngoài. Sau đó, chúng ta di chuyển con trỏ của trình tạo tài liệu đến ô đầu tiên của bảng bên ngoài và tạo bảng mới bên trong bằng cách chèn các ô và nội dung.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với bảng lồng nhau. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Bảng lồng nhau bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Lệnh gọi này rất quan trọng để tạo một bảng lồng nhau trong bảng đầu tiên.
	// Nếu không có lệnh gọi này, các ô được chèn bên dưới sẽ được thêm vào bảng bên ngoài.
	builder.EndTable();
	// Di chuyển đến ô đầu tiên của bảng bên ngoài.
	builder.MoveTo(cell.FirstParagraph);
	// Xây dựng bảng bên trong.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách tạo bảng lồng nhau trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể tạo các bảng lồng nhau theo nhu cầu cụ thể của mình trong tài liệu Word theo chương trình.
