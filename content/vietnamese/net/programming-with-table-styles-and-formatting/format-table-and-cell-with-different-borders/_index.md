---
title: Định dạng bảng và ô có viền khác nhau
linktitle: Định dạng bảng và ô có viền khác nhau
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước định dạng bảng và ô có đường viền khác nhau bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để định dạng bảng và ô có các đường viền khác nhau bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách áp dụng đường viền tùy chỉnh cho bảng và ô cụ thể trong tài liệu Word bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là vị trí bạn muốn lưu tài liệu Word đã chỉnh sửa của mình. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo tài liệu mới và trình tạo tài liệu
 Tiếp theo, bạn cần tạo một phiên bản mới của`Document` lớp và một hàm tạo tài liệu cho tài liệu đó.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Bắt đầu một bảng mới và thêm ô
Để bắt đầu tạo bảng, chúng ta sử dụng`StartTable()` của trình tạo tài liệu, sau đó chúng ta thêm các ô vào bảng bằng cách sử dụng`InsertCell()` phương thức và chúng tôi ghi nội dung của các ô vào bằng cách sử dụng`Writeln()` phương pháp.

```csharp
Table table = builder. StartTable();
builder.InsertCell();
// Đặt đường viền cho toàn bộ bảng.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Đặt phần đệm cho ô này.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Chỉ định phần đệm ô khác cho ô thứ hai.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Xóa định dạng ô từ các thao tác trước đó.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Tạo đường viền dày hơn cho ô đầu tiên trong hàng này. Nó sẽ khác
// so với các đường viền được xác định cho bảng.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Bước 4: Lưu tài liệu

  sửa đổi
Cuối cùng lưu tài liệu đã sửa đổi vào một tập tin. Bạn có thể chọn tên và vị trí thích hợp cho tài liệu đầu ra.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Xin chúc mừng! Bây giờ bạn đã định dạng một bảng và một ô có các đường viền khác nhau bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho Định dạng bảng và ô có đường viền khác nhau bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//Đặt đường viền cho toàn bộ bảng.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Đặt bóng cho ô này.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// Chỉ định màu bóng ô khác cho ô thứ hai.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
// Xóa định dạng ô khỏi các thao tác trước đó.
builder.CellFormat.ClearFormatting();
builder.InsertCell();
// Tạo đường viền lớn hơn cho ô đầu tiên của hàng này. Điều này sẽ khác
// so với các đường viền được thiết lập cho bảng.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách định dạng bảng và ô có các đường viền khác nhau bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng tùy chỉnh viền bảng và ô trong tài liệu Word của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể cải thiện cách trình bày trực quan các tài liệu Word của mình và đáp ứng các nhu cầu cụ thể.