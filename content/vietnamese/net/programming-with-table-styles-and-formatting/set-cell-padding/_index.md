---
title: Đặt phần đệm ô
linktitle: Đặt phần đệm ô
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước cách đặt lề ô bảng bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để đặt lề ô bảng bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách điều chỉnh lề trái, trên, phải và dưới (khoảng trắng) của nội dung ô trong bảng trong tài liệu Word bằng Aspose.Words for .NET.

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
builder. StartTable();
builder. InsertCell();
```

## Bước 4: Đặt lề ô
 Bây giờ chúng ta có thể thiết lập lề ô bằng cách sử dụng`SetPaddings()` phương pháp của`CellFormat` sự vật. Lề được xác định theo điểm và được chỉ định theo thứ tự trái, trên, phải và dưới.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Bước 5: Thêm nội dung vào ô
 Sau đó, chúng ta có thể thêm nội dung vào ô bằng cách sử dụng trình tạo tài liệu`Writeln()` phương pháp.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Bước 6: Hoàn thiện bảng và lưu tài liệu
 Cuối cùng, chúng ta hoàn thành việc tạo bảng bằng cách sử dụng`EndRow()` phương pháp và`EndTable()`, sau đó chúng tôi lưu tài liệu đã sửa đổi vào một tệp.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Mã nguồn mẫu cho Đặt phần đệm ô bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Đặt khoảng cách (theo điểm) để thêm vào bên trái/trên cùng/phải/dưới cùng của nội dung ô.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách đặt lề của ô bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng điều chỉnh lề ô để tạo khoảng trắng ở bên trái, trên cùng, bên phải và dưới cùng của nội dung trong bảng trong tài liệu Word của bạn. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể tùy chỉnh định dạng của bảng theo nhu cầu cụ thể của mình.