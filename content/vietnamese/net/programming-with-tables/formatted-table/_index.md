---
title: Bảng được định dạng
linktitle: Bảng được định dạng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo bảng được định dạng trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/formatted-table/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách tạo bảng được định dạng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể tạo các bảng có định dạng tùy chỉnh trong tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tạo tài liệu và khởi tạo trình tạo tài liệu
Để bắt đầu xây dựng bảng được định dạng, chúng ta cần tạo một tài liệu mới và khởi tạo trình tạo tài liệu. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và khởi tạo trình tạo tài liệu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Xây dựng bảng được định dạng
Tiếp theo, chúng ta sẽ xây dựng bảng được định dạng bằng các phương thức do trình tạo tài liệu cung cấp. Sử dụng mã sau đây:

```csharp
// Bắt đầu xây dựng mảng
Table table = builder. StartTable();

// Xây dựng dòng tiêu đề của bảng
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Xây dựng phần thân mảng
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Kết thúc việc xây dựng mảng
builder. EndTable();
```

 Ở đây chúng tôi sử dụng trình tạo tài liệu để xây dựng bảng từng bước. Chúng tôi bắt đầu bằng cách gọi`StartTable()` để khởi tạo bảng. Sau đó chúng tôi sử dụng`InsertCell()` để chèn ô và`Write()` để thêm nội dung vào từng ô. Chúng tôi cũng sử dụng các thuộc tính định dạng khác nhau để xác định định dạng của hàng, ô và văn bản trong bảng.

## Bước 4: Lưu tài liệu
Cuối cùng chúng ta cần lưu tài liệu chứa bảng đã định dạng. Sử dụng mã sau đây:

```csharp
// Lưu tài liệu
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Bảng được định dạng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Định dạng toàn bảng phải được áp dụng sau khi có ít nhất một hàng trong bảng.
	table.LeftIndent = 20.0;
	// Đặt chiều cao và xác định quy tắc chiều cao cho hàng tiêu đề.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Chúng ta không cần chỉ định chiều rộng của ô này vì nó được kế thừa từ ô trước đó.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Đặt lại chiều cao và xác định quy tắc chiều cao khác cho thân bảng.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Đặt lại định dạng phông chữ.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách tạo bảng được định dạng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể tạo các bảng tùy chỉnh với định dạng cụ thể trong tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn trình bày và cấu trúc dữ liệu của mình theo cách có tổ chức và hấp dẫn trực quan.