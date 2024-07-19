---
title: Lặp lại hàng trên các trang tiếp theo
linktitle: Lặp lại hàng trên các trang tiếp theo
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách lặp lại các hàng trong bảng trên các trang tiếp theo trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách lặp lại các hàng của bảng trên các trang tiếp theo của tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể chỉ định các hàng sẽ lặp lại trên các trang tiếp theo của bảng trong tài liệu Word của mình.

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

## Bước 3: Xây dựng bảng với các hàng lặp lại
Tiếp theo, chúng ta sẽ tạo một bảng có các hàng lặp lại trên các trang tiếp theo. Sử dụng mã sau đây:

```csharp
// Đầu bảng
builder. StartTable();

// Cấu hình các tham số dòng đầu tiên (dòng tiêu đề)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Chèn ô đầu tiên của hàng đầu tiên
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Chèn ô thứ hai của hàng đầu tiên
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Cấu hình thông số các dòng sau
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Vòng lặp để chèn các ô vào các hàng sau
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Cuối bảng
builder. EndTable();
```

 Ở đây chúng tôi sử dụng trình tạo tài liệu để xây dựng một bảng có hai hàng tiêu đề và nhiều hàng dữ liệu. Các`RowFormat.HeadingFormat` các tham số được sử dụng để đánh dấu các hàng tiêu đề cần được lặp lại trên các trang tiếp theo.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng là Mỹ

  cần lưu tài liệu đã sửa đổi với các hàng tiêu đề được lặp lại trên các trang tiếp theo của bảng. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho các hàng lặp lại trên các trang tiếp theo bằng cách sử dụng Aspose.Words for .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách lặp lại các hàng của bảng trên các trang tiếp theo của tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể chỉ định những dòng nào sẽ lặp lại theo nhu cầu cụ thể của mình trong tài liệu Word.