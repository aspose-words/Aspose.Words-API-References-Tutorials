---
title: Sửa đổi định dạng hàng
linktitle: Sửa đổi định dạng hàng
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thay đổi định dạng hàng trong bảng bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/modify-row-formatting/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để thay đổi định dạng của một hàng trong bảng bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách thay đổi đường viền, chiều cao và ngắt dòng của một hàng trong bảng trong tài liệu Word bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là nơi chứa tài liệu Word của bạn. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu hiện có
 Tiếp theo, bạn cần tải tài liệu Word hiện có vào một phiên bản của`Document` lớp học.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Bước 3: Truy cập dòng cần sửa đổi
 Để thay đổi định dạng của một hàng trong bảng, chúng ta cần điều hướng đến hàng cụ thể trong bảng. Chúng tôi sử dụng`GetChild()`Và`FirstRow` các phương thức để lấy tham chiếu đến hàng đầu tiên của bảng.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Row firstRow = table.FirstRow;
```

## Bước 4: Thay đổi định dạng hàng
 Bây giờ chúng ta có thể thay đổi định dạng hàng bằng cách sử dụng các thuộc tính của`RowFormat` lớp học. Ví dụ: chúng ta có thể xóa đường viền dòng, đặt chiều cao tự động và cho phép ngắt dòng.

```csharp
firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
firstRow.RowFormat.HeightRule = HeightRule.Auto;
firstRow.RowFormat.AllowBreakAcrossPages = true;
```

### Mã nguồn mẫu để Sửa đổi định dạng hàng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Lấy hàng đầu tiên trong bảng.
	Row firstRow = table.FirstRow;
	firstRow.RowFormat.Borders.LineStyle = LineStyle.None;
	firstRow.RowFormat.HeightRule = HeightRule.Auto;
	firstRow.RowFormat.AllowBreakAcrossPages = true;
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách thay đổi định dạng của một hàng trong bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng điều chỉnh đường viền, chiều cao và ngắt dòng của các hàng trong bảng trong tài liệu Word của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể tùy chỉnh bố cục trực quan của bảng theo nhu cầu cụ thể của mình.