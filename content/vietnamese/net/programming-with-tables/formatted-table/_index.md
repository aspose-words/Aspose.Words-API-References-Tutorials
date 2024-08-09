---
title: Bảng được định dạng
linktitle: Bảng được định dạng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo và định dạng bảng trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước chi tiết này.
type: docs
weight: 10
url: /vi/net/programming-with-tables/formatted-table/
---
## Giới thiệu

Tạo và định dạng bảng trong tài liệu Word theo chương trình có vẻ như là một nhiệm vụ khó khăn, nhưng với Aspose.Words dành cho .NET, công việc này trở nên đơn giản và dễ quản lý. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách tạo bảng được định dạng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ đề cập đến mọi thứ từ việc thiết lập môi trường cho đến lưu tài liệu của bạn bằng một bảng được định dạng đẹp mắt.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy đảm bảo bạn có mọi thứ bạn cần:

1. Thư viện Aspose.Words for .NET: Tải xuống từ[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Một IDE như Visual Studio.
3. .NET Framework: Đảm bảo bạn đã cài đặt .NET Framework trên máy của mình.

## Nhập không gian tên

Trước khi viết mã thực tế, bạn cần nhập các không gian tên cần thiết:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, bạn cần xác định đường dẫn nơi tài liệu của bạn sẽ được lưu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế mà bạn muốn lưu tài liệu.

## Bước 2: Khởi tạo Document và DocumentBuilder

Bây giờ, hãy khởi tạo một tài liệu mới và đối tượng DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 các`DocumentBuilder` là một lớp trợ giúp giúp đơn giản hóa quá trình xây dựng tài liệu.

## Bước 3: Bắt đầu bảng

 Tiếp theo, bắt đầu tạo bảng bằng cách sử dụng`StartTable` phương pháp.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

Việc chèn một ô là cần thiết để bắt đầu bảng.

## Bước 4: Áp dụng định dạng toàn bảng

Bạn có thể áp dụng định dạng ảnh hưởng đến toàn bộ bảng. Ví dụ: đặt thụt lề trái:

```csharp
table.LeftIndent = 20.0;
```

## Bước 5: Định dạng hàng tiêu đề

Đặt chiều cao, căn chỉnh và các thuộc tính khác cho hàng tiêu đề.

```csharp
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");
```

Trong bước này, chúng ta làm nổi bật hàng tiêu đề bằng cách đặt màu nền, cỡ chữ và căn chỉnh.

## Bước 6: Chèn các ô tiêu đề bổ sung

Chèn thêm ô cho hàng tiêu đề:

```csharp
builder.InsertCell();
builder.Write("Header Row,\n Cell 2");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");
builder.EndRow();
```

## Bước 7: Định dạng các dòng nội dung

Sau khi thiết lập tiêu đề, định dạng phần thân của bảng:

```csharp
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;
```

## Bước 8: Chèn hàng nội dung

Chèn các hàng nội dung có nội dung:

```csharp
builder.InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Row 1, Cell 1 Content");
builder.InsertCell();
builder.Write("Row 1, Cell 2 Content");
builder.InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Row 1, Cell 3 Content");
builder.EndRow();
```

Lặp lại cho các hàng bổ sung:

```csharp
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
```

## Bước 9: Lưu tài liệu

Cuối cùng, lưu tài liệu vào thư mục được chỉ định:

```csharp
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Thao tác này sẽ tạo và lưu tài liệu Word với bảng được định dạng.

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn có thể tạo bảng được định dạng phù hợp trong tài liệu Word bằng Aspose.Words cho .NET. Thư viện mạnh mẽ này giúp bạn dễ dàng thao tác theo chương trình với các tài liệu Word, giúp bạn tiết kiệm thời gian và công sức.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để tạo, chỉnh sửa và chuyển đổi tài liệu Word theo chương trình.

### Tôi có thể sử dụng các màu khác nhau cho các hàng khác nhau không?
Có, bạn có thể áp dụng các định dạng khác nhau, bao gồm cả màu sắc, cho các hàng hoặc ô khác nhau.

### Aspose.Words cho .NET có miễn phí không?
 Aspose.Words for .NET là một thư viện trả phí, nhưng bạn có thể có được[dùng thử miễn phí](https://releases.aspose.com/).

### Làm cách nào để nhận được hỗ trợ cho Aspose.Words cho .NET?
 Bạn có thể nhận được sự hỗ trợ từ[Diễn đàn cộng đồng](https://forum.aspose.com/c/words/8).

### Tôi có thể tạo các loại tài liệu khác bằng Aspose.Words cho .NET không?
Có, Aspose.Words for .NET hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm PDF, HTML và TXT.