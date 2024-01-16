---
title: Xây dựng bảng với phong cách
linktitle: Xây dựng bảng với phong cách
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xây dựng bảng với kiểu tùy chỉnh bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để xây dựng bảng theo kiểu bằng cách sử dụng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách tạo bảng với kiểu tùy chỉnh trong tài liệu Word của mình bằng Aspose.Words cho .NET.

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

## Bước 3: Bắt đầu một bảng mới và chèn một ô
 Để bắt đầu xây dựng bảng, chúng ta sử dụng`StartTable()` của trình tạo tài liệu, sau đó chúng ta chèn một ô vào bảng bằng cách sử dụng`InsertCell()` phương pháp.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Bước 4: Xác định kiểu dáng của bảng
 Bây giờ chúng ta có thể thiết lập kiểu bảng bằng cách sử dụng`StyleIdentifier` tài sản. Trong ví dụ này, chúng tôi đang sử dụng kiểu "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Bước 5: Áp dụng các tùy chọn kiểu cho bảng
 Chúng ta có thể chỉ định những đặc điểm nào sẽ được định dạng theo kiểu bằng cách sử dụng`StyleOptions`thuộc tính của mảng. Trong ví dụ này, chúng tôi áp dụng các tùy chọn sau: "FirstColumn", "RowBands" và "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Bước 6: Tự động điều chỉnh kích thước bảng
 Để tự động điều chỉnh kích thước của mảng dựa trên nội dung của nó, chúng ta sử dụng`AutoFit()` phương pháp với`AutoFitBehavior.AutoFitToContents` hành vi.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Bước 7: Thêm nội dung vào ô
 Bây giờ chúng ta có thể thêm nội dung vào các ô bằng cách sử dụng`Writeln()` Và`InsertCell()` phương pháp của người xây dựng tài liệu. Trong ví dụ này, chúng tôi thêm tiêu đề cho "Mặt hàng" và "Số lượng (

kg)" và dữ liệu tương ứng.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Bước 8: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng tôi lưu tài liệu đã sửa đổi vào một tệp. Bạn có thể chọn tên và vị trí thích hợp cho tài liệu đầu ra.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Xin chúc mừng! Bây giờ bạn đã xây dựng một bảng có kiểu tùy chỉnh bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho Xây dựng bảng có kiểu bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Chúng ta phải chèn ít nhất một hàng trước khi thiết lập bất kỳ định dạng bảng nào.
	builder.InsertCell();
	// Đặt kiểu bảng được sử dụng dựa trên mã định danh kiểu duy nhất.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Áp dụng những tính năng nào sẽ được định dạng theo kiểu.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách xây dựng một bảng theo kiểu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng tùy chỉnh kiểu bảng trong tài liệu Word của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể cải thiện cách trình bày trực quan các tài liệu Word của mình và đáp ứng các nhu cầu cụ thể.