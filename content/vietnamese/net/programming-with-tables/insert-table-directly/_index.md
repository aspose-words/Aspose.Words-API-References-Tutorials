---
title: Chèn bảng trực tiếp
linktitle: Chèn bảng trực tiếp
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn bảng trực tiếp vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/insert-table-directly/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách chèn trực tiếp bảng vào tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể chèn bảng trực tiếp vào tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tạo tài liệu và bảng
Để bắt đầu Xử lý từ với mảng, chúng ta cần tạo một tài liệu mới và khởi tạo mảng. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu
Document doc = new Document();

//Tạo mảng
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Xây dựng mảng
Tiếp theo, chúng ta sẽ xây dựng bảng bằng cách thêm hàng và ô. Sử dụng đoạn mã sau làm ví dụ:

```csharp
// Tạo hàng đầu tiên
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Tạo ô đầu tiên
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Nhân đôi ô cho ô thứ hai trong hàng
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Ở đây chúng ta tạo một hàng với`AllowBreakAcrossPages` thuộc tính được đặt thành`true` để cho phép ngắt trang giữa các hàng. Sau đó, chúng tôi tạo một ô có nền màu, chiều rộng cố định và nội dung văn bản được chỉ định. Sau đó chúng ta nhân đôi ô này để tạo ô thứ hai trong hàng.

## Bước 4: Bảng tự động điều chỉnh
Chúng ta có thể áp dụng các điều chỉnh tự động cho bảng để định dạng chính xác. Sử dụng mã sau đây:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Dòng mã này áp dụng tính năng tự động điều chỉnh dựa trên độ rộng cột cố định.

## Bước 5: Đăng ký

  tài liệu sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với bảng được chèn trực tiếp. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Chèn bảng trực tiếp bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Chúng ta bắt đầu bằng cách tạo đối tượng bảng. Lưu ý rằng chúng ta phải truyền đối tượng tài liệu
	//tới hàm tạo của mỗi nút. Điều này là do mọi nút chúng tôi tạo phải thuộc về
	// tới một tài liệu nào đó.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Ở đây chúng ta có thể gọi EnsureMinimum để tạo các hàng và ô cho chúng ta. Phương pháp này được sử dụng
	// để đảm bảo rằng nút được chỉ định là hợp lệ. Trong trường hợp này, một bảng hợp lệ phải có ít nhất một Hàng và một ô.
	// Thay vào đó, chúng ta sẽ tự xử lý việc tạo hàng và bảng.
	// Đây sẽ là cách tốt nhất để làm điều này nếu chúng ta tạo một bảng bên trong một thuật toán.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Bây giờ chúng ta có thể áp dụng bất kỳ cài đặt tự động điều chỉnh nào.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Sau đó, chúng tôi sẽ lặp lại quy trình cho các ô và hàng khác trong bảng.
	// Chúng ta cũng có thể tăng tốc mọi thứ bằng cách sao chép các ô và hàng hiện có.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách chèn trực tiếp bảng vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể chèn bảng trực tiếp vào tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn tạo và tùy chỉnh các bảng theo nhu cầu cụ thể của mình.