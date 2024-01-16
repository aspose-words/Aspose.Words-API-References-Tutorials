---
title: Tạo kiểu bảng
linktitle: Tạo kiểu bảng
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để tạo kiểu bảng tùy chỉnh bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/create-table-style/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để tạo kiểu bảng bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách tạo kiểu tùy chỉnh cho các bảng trong tài liệu Word bằng Aspose.Words cho .NET.

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
Để bắt đầu tạo bảng, chúng ta sử dụng`StartTable()` của trình tạo tài liệu, sau đó chúng ta thêm các ô vào bảng bằng cách sử dụng`InsertCell()` phương thức và chúng tôi ghi nội dung của các ô vào bằng cách sử dụng`Write()` phương pháp.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Bước 4: Tạo kiểu bảng
 Bây giờ chúng ta có thể tạo kiểu bảng bằng cách sử dụng`TableStyle` lớp học và`Add()` phương pháp từ tài liệu`s `Bộ sưu tập Styles. Chúng tôi xác định các thuộc tính của kiểu, chẳng hạn như đường viền, lề và phần đệm.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Bước 5: Áp dụng kiểu bảng cho bảng
 Cuối cùng, chúng ta áp dụng kiểu bảng mà chúng ta đã tạo cho bảng bằng cách sử dụng`Style` thuộc tính của bảng.

```csharp
table.Style = tableStyle;
```

## Bước 6: Lưu tài liệu đã sửa đổi
Cuối cùng lưu tài liệu đã sửa đổi vào một tập tin. Bạn có thể chọn tên và vị trí thích hợp cho tài liệu đầu ra.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Xin chúc mừng! Bây giờ bạn đã tạo kiểu tùy chỉnh cho bảng của mình bằng Aspose.Words cho .NET.

### Mã nguồn mẫu để Tạo kiểu bảng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách tạo kiểu bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng tùy chỉnh kiểu bảng trong tài liệu Word của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể cải thiện cách trình bày trực quan các tài liệu Word của mình và đáp ứng các nhu cầu cụ thể.