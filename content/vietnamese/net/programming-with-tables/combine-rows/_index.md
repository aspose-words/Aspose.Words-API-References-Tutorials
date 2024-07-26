---
title: Kết hợp các hàng
linktitle: Kết hợp các hàng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách kết hợp các hàng của bảng trong tài liệu Word với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/combine-rows/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Words cho .NET để kết hợp các hàng bảng trong tài liệu Word. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể thao tác và hợp nhất các hàng trong bảng trong tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Load tài liệu và truy cập vào bảng
Để bắt đầu Xử lý từ bằng bảng, chúng ta cần tải tài liệu chứa chúng và truy cập chúng. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Tables.docx");

// Truy cập vào bảng
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Kết hợp các hàng trong bảng
Tiếp theo, chúng ta sẽ gộp các hàng của bảng thứ hai vào cuối bảng thứ nhất. Sử dụng mã sau đây:

```csharp
// Sự kết hợp của các hàng trong bảng
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Ở đây chúng tôi sử dụng một`while` vòng lặp để lặp qua tất cả các hàng của mảng thứ hai và thêm chúng vào cuối mảng đầu tiên bằng cách sử dụng`Add` phương pháp. Tiếp theo, chúng tôi xóa bảng thứ hai khỏi tài liệu bằng cách sử dụng`Remove` phương pháp.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với các hàng của bảng được kết hợp. Sử dụng mã sau đây:

```csharp
// Lưu tài liệu đã sửa đổi
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Kết hợp các hàng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Các hàng từ bảng thứ hai sẽ được thêm vào cuối bảng đầu tiên.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Nối tất cả các hàng từ bảng hiện tại vào các bảng tiếp theo
	// với số lượng ô và chiều rộng khác nhau có thể được nối vào một bảng.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách kết hợp các hàng bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể thao tác các hàng trong bảng trong tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn hợp nhất và sắp xếp dữ liệu của mình thành một bảng một cách hiệu quả.