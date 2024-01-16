---
title: Cài đặt chiều rộng ưa thích
linktitle: Cài đặt chiều rộng ưa thích
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt độ rộng ô bảng ưa thích trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/preferred-width-settings/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách đặt cài đặt độ rộng ưa thích cho các ô bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể chỉ định các độ rộng ưu tiên khác nhau cho các ô bảng trong tài liệu Word của mình.

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

## Bước 3: Xây dựng bảng với chiều rộng ưa thích
Tiếp theo, chúng ta sẽ tạo một bảng có ba ô có độ rộng ưu tiên khác nhau. Sử dụng mã sau đây:

```csharp
// Đầu bảng
builder. StartTable();

// Chèn một ô có kích thước tuyệt đối
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Chèn một ô có kích thước tương đối (theo phần trăm)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Chèn một ô có kích thước tự động
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Cuối bảng
builder. EndTable();
```

Ở đây chúng tôi sử dụng trình tạo tài liệu để xây dựng một bảng có ba ô. Ô đầu tiên có chiều rộng ưu tiên là 40 điểm, ô thứ hai có chiều rộng ưu tiên là 20% chiều rộng của bảng và ô thứ ba có chiều rộng ưu tiên tự động điều chỉnh

  tùy thuộc vào không gian có sẵn.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với cài đặt độ rộng ưa thích được xác định cho các ô trong bảng. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Cài đặt độ rộng ưa thích bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Chèn một hàng trong bảng gồm ba ô có độ rộng ưu tiên khác nhau.
	builder.StartTable();
	// Chèn một ô có kích thước tuyệt đối.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Chèn một ô có kích thước tương đối (phần trăm).
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Chèn một ô có kích thước tự động.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt cài đặt độ rộng ưa thích cho các ô bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể tùy chỉnh độ rộng ô trong bảng theo nhu cầu cụ thể trong tài liệu Word của mình.