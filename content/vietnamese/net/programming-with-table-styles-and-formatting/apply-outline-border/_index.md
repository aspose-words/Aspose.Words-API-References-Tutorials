---
title: Áp dụng đường viền phác thảo
linktitle: Áp dụng đường viền phác thảo
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để áp dụng đường viền phác thảo cho bảng bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để áp dụng đường viền phác thảo cho bảng bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ về cách thao tác viền bảng trong tài liệu Word bằng Aspose.Words cho .NET.

## Bước 1: Xác định thư mục tài liệu
Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Đây là nơi tài liệu Word của bạn được lưu trữ. Thay thế "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu lên
 Tiếp theo, bạn cần tải tài liệu Word vào một phiên bản của`Document` lớp học.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Bước 3: Truy cập vào bảng
 Để áp dụng đường viền phác thảo, chúng ta cần truy cập vào bảng trong tài liệu. Các`Table` lớp đại diện cho một bảng trong Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Bước 4: Căn chỉnh bảng vào giữa trang
 Bây giờ chúng ta có thể căn chỉnh bảng vào giữa trang bằng cách sử dụng`Alignment` thuộc tính của bảng.

```csharp
table. Alignment = Table Alignment. Center;
```

## Bước 5: Xóa viền bảng hiện có.
Để bắt đầu với đường viền phác thảo mới, trước tiên chúng ta cần xóa tất cả các đường viền hiện có khỏi bảng. Điều này có thể được thực hiện bằng cách sử dụng`ClearBorders()` phương pháp.

```csharp
table. ClearBorders();
```

## Bước 6: Xác định đường viền xanh xung quanh bảng
 Bây giờ chúng ta có thể thiết lập đường viền màu xanh xung quanh bảng bằng cách sử dụng`SetBorder()` phương pháp cho mỗi cạnh của bảng. Trong ví dụ này, chúng tôi đang sử dụng đường viền loại "Đơn" có độ dày 1,5 điểm và có màu xanh lục.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Bước 7: Tô màu nền cho các ô.
Để cải thiện cách trình bày trực quan của bảng, chúng ta có thể tô màu nền cho các ô.

ý tưởng. Trong ví dụ này, chúng tôi đang sử dụng màu xanh nhạt.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Bước 8: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng tôi lưu tài liệu đã sửa đổi vào một tệp. Bạn có thể chọn tên và vị trí thích hợp cho tài liệu đầu ra.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Xin chúc mừng! Bây giờ bạn đã áp dụng đường viền phác thảo cho bảng bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho Áp dụng đường viền phác thảo bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Căn chỉnh bảng vào giữa trang.
	table.Alignment = TableAlignment.Center;
	//Xóa mọi đường viền hiện có khỏi bảng.
	table.ClearBorders();
	// Đặt đường viền màu xanh lá cây xung quanh bàn nhưng không viền bên trong.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Tô màu các ô bằng màu xanh nhạt.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách áp dụng đường viền phác thảo cho bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng tích hợp chức năng này vào các dự án C# của mình. Thao tác định dạng bảng là một khía cạnh thiết yếu của quá trình xử lý tài liệu và Aspose.Words cung cấp API mạnh mẽ và linh hoạt để đạt được điều này. Với kiến thức này, bạn có thể cải thiện cách trình bày trực quan các tài liệu Word của mình và đáp ứng các yêu cầu cụ thể.