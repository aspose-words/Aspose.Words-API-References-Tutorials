---
title: Đặt định dạng hàng bảng
linktitle: Đặt định dạng hàng bảng
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thiết lập định dạng hàng trong bảng bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để đặt định dạng hàng trong bảng bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách điều chỉnh chiều cao và khoảng đệm của một hàng trong bảng trong tài liệu Word bằng Aspose.Words cho .NET.

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

## Bước 3: Bắt đầu một bảng mới và thêm một ô
Để bắt đầu tạo bảng, chúng ta sử dụng`StartTable()` của hàm tạo tài liệu, sau đó chúng ta thêm một ô vào bảng bằng cách sử dụng`InsertCell()` phương pháp.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Bước 4: Xác định định dạng dòng
 Bây giờ chúng ta có thể thiết lập định dạng hàng bằng cách truy cập vào`RowFormat` đối tượng của`DocumentBuilder` sự vật. Chúng ta có thể đặt chiều cao của dòng và lề (phần đệm) bằng các thuộc tính tương ứng.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Bước 5: Đặt lề bảng
 Tiếp theo, chúng ta có thể đặt phần đệm của bảng bằng cách truy cập các thuộc tính tương ứng của`Table` sự vật. Các lề này sẽ được áp dụng cho tất cả các hàng của bảng.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Bước 6: Thêm nội dung vào hàng
 Cuối cùng, chúng ta có thể thêm nội dung vào dòng bằng cách sử dụng trình tạo tài liệu`Writeln()` phương pháp.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Bước 7: Hoàn thiện bảng và lưu tài liệu
TRONG

 kết thúc, chúng ta hoàn thành việc tạo bảng bằng cách sử dụng`EndRow()` Và`EndTable()` phương thức, sau đó chúng tôi lưu tài liệu đã sửa đổi vào một tệp.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Mã nguồn mẫu cho Đặt định dạng hàng bảng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Các thuộc tính định dạng này được đặt trên bảng và được áp dụng cho tất cả các hàng trong bảng.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách thiết lập định dạng hàng trong bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng điều chỉnh chiều cao và lề của hàng trong bảng trong tài liệu Word của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể tùy chỉnh bố cục trực quan của bảng theo nhu cầu cụ thể của mình.