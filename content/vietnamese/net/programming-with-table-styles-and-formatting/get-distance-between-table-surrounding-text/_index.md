---
title: Nhận khoảng cách giữa văn bản xung quanh bảng
linktitle: Nhận khoảng cách giữa văn bản xung quanh bảng
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để lấy khoảng cách giữa văn bản và bảng trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình từng bước để tính khoảng cách giữa văn bản xung quanh trong bảng bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# đi kèm và cung cấp cho bạn hướng dẫn toàn diện để giúp bạn hiểu và triển khai tính năng này trong các dự án của riêng bạn. Ở cuối hướng dẫn này, bạn sẽ biết cách truy cập các khoảng cách khác nhau giữa bảng và văn bản xung quanh trong tài liệu Word bằng Aspose.Words cho .NET.

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

## Bước 3: Lấy khoảng cách giữa bảng và văn bản xung quanh
 Để có được khoảng cách giữa bảng và văn bản xung quanh, chúng ta cần truy cập vào bảng trong tài liệu bằng cách sử dụng`GetChild()` phương pháp và`NodeType.Table` tài sản. Sau đó chúng ta có thể hiển thị các khoảng cách khác nhau bằng cách sử dụng thuộc tính mảng`DistanceTop`, `DistanceBottom`, `DistanceRight`Và`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Mã nguồn mẫu để lấy khoảng cách giữa văn bản xung quanh bảng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách lấy khoảng cách giữa văn bản xung quanh trong bảng bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng truy cập các khoảng cách khác nhau giữa bảng và văn bản xung quanh trong tài liệu Word của mình. Aspose.Words cung cấp API mạnh mẽ và linh hoạt để thao tác và định dạng bảng trong tài liệu của bạn. Với kiến thức này, bạn có thể phân tích bố cục của các bảng liên quan đến văn bản và đáp ứng các nhu cầu cụ thể.