---
title: Mở rộng định dạng trên ô và hàng từ kiểu
linktitle: Mở rộng định dạng trên ô và hàng từ kiểu
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để mở rộng định dạng cho các ô và hàng từ kiểu bảng bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để mở rộng định dạng cho các ô và hàng từ một kiểu bằng cách sử dụng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách áp dụng định dạng kiểu bảng cho các ô và hàng cụ thể trong tài liệu Word bằng Aspose.Words cho .NET.


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

## Bước 3: Về ô đầu tiên của bảng đầu tiên
 Để bắt đầu, chúng ta cần điều hướng đến ô đầu tiên của bảng đầu tiên trong tài liệu. Chúng tôi sử dụng`GetChild()` Và`FirstRow.FirstCell` phương pháp để có được tham chiếu đến ô đầu tiên.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Bước 4: Hiển thị định dạng ô ban đầu
Trước khi mở rộng kiểu của bảng, chúng ta hiển thị màu nền hiện tại của ô. Phần này phải trống vì định dạng hiện tại được lưu trữ theo kiểu bảng.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Bước 5: Mở rộng kiểu bảng sang định dạng trực tiếp
 Bây giờ chúng ta mở rộng các kiểu bảng để định dạng trực tiếp bằng cách sử dụng`ExpandTableStylesToDirectFormatting()` phương pháp.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Bước 6: Hiển thị định dạng ô sau khi mở rộng kiểu
Bây giờ chúng ta hiển thị màu nền của ô sau khi Expanding các kiểu bảng. Màu nền xanh lam nên được áp dụng từ kiểu bảng.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Mã nguồn mẫu để mở rộng định dạng trên ô và hàng từ kiểu bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Lấy ô đầu tiên của bảng đầu tiên trong tài liệu.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Đầu tiên in màu của bóng ô.
	// Phần này phải trống vì phần tô bóng hiện tại được lưu trữ theo kiểu bảng.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Bây giờ in bóng ô sau khi mở rộng kiểu bảng.
	// Màu nền xanh lam lẽ ra phải được áp dụng từ kiểu bảng.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách mở rộng định dạng sang ô và hàng từ kiểu bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng áp dụng định dạng kiểu bảng cho các ô và hàng cụ thể trong tài liệu Word của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể tùy chỉnh thêm bố cục và cách trình bày tài liệu Word của mình.