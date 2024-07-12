---
title: Áp dụng định dạng hàng
linktitle: Áp dụng định dạng hàng
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước áp dụng định dạng hàng cho bảng bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để áp dụng định dạng hàng cho bảng bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ về cách định dạng các hàng trong bảng trong tài liệu Word bằng Aspose.Words cho .NET.

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

## Bước 3: Bắt đầu một bảng mới
 Để áp dụng định dạng hàng, trước tiên chúng ta phải bắt đầu một bảng mới bằng cách sử dụng`StartTable()` phương thức của hàm tạo tài liệu.

```csharp
Table table = builder. StartTable();
```

## Bước 4: Chèn ô và chuyển sang định dạng hàng
Bây giờ chúng ta có thể chèn một ô vào bảng và truy cập định dạng hàng cho ô đó bằng cách sử dụng trình tạo tài liệu`InsertCell()`Và`RowFormat` phương pháp.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Bước 5: Đặt chiều cao hàng
 Để thiết lập chiều cao của hàng, chúng ta sử dụng`Height`Và`HeightRule` thuộc tính của định dạng hàng. Trong ví dụ này, chúng tôi đặt chiều cao hàng là 100 điểm và sử dụng`Exactly` luật lệ.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Bước 6: Xác định định dạng bảng
 Một số thuộc tính định dạng có thể được đặt trên chính bảng và được áp dụng cho tất cả các hàng của bảng. Trong ví dụ này, chúng tôi đặt thuộc tính lề bảng bằng cách sử dụng`LeftPadding`, `RightPadding`, `TopPadding`Và`BottomPadding` của cải.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Bước 7: Thêm nội dung vào hàng
Bây giờ chúng ta có thể

 Chúng ta sẽ thêm nội dung vào dòng bằng cách sử dụng các phương thức của hàm tạo tài liệu. Trong ví dụ này, chúng tôi sử dụng`Writeln()` phương pháp thêm văn bản vào dòng.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Bước 8: Hoàn thiện dòng và bảng
 Khi chúng ta đã thêm nội dung vào hàng, chúng ta có thể kết thúc hàng bằng cách sử dụng`EndRow()` phương pháp và sau đó kết thúc bảng bằng cách sử dụng`EndTable()` phương pháp.

```csharp
builder. EndRow();
builder. EndTable();
```

## Bước 9: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng tôi lưu tài liệu đã sửa đổi vào một tệp. Bạn có thể chọn tên và vị trí thích hợp cho tài liệu đầu ra.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Xin chúc mừng! Bây giờ bạn đã áp dụng định dạng hàng cho bảng bằng Aspose.Words for .NET.

### Mã nguồn mẫu cho Áp dụng định dạng hàng bằng Aspose.Words cho .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách áp dụng định dạng hàng cho bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng tích hợp chức năng này vào các dự án C# của mình. Thao tác định dạng hàng trong bảng là một khía cạnh thiết yếu của quá trình xử lý tài liệu và Aspose.Words cung cấp API mạnh mẽ và linh hoạt để đạt được điều này. Với kiến thức này, bạn có thể cải thiện cách trình bày trực quan các tài liệu Word của mình và đáp ứng các yêu cầu cụ thể.