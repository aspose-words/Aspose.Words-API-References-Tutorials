---
title: Định dạng hàng Tắt ngắt trên các trang
linktitle: Định dạng hàng Tắt ngắt trên các trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tắt tính năng ngắt dòng cho một bảng trên nhiều trang trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/row-format-disable-break-across-pages/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách tắt tính năng ngắt dòng của bảng nhiều trang trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể tắt tính năng ngắt dòng cho tất cả các hàng trong bảng trong tài liệu Word của mình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tải tài liệu
Để bắt đầu Xử lý văn bản với tài liệu, hãy làm theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn và cung cấp tên tệp chính xác.

## Bước 3: Tắt tính năng ngắt hàng của bảng
Tiếp theo, chúng tôi sẽ tắt tính năng ngắt hàng cho tất cả các hàng trong bảng. Sử dụng mã sau đây:

```csharp
// Truy xuất bảng
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Vô hiệu hóa ngắt hàng cho tất cả các hàng trong bảng
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Ở đây, chúng tôi sử dụng tài liệu để tìm nạp bảng đầu tiên và sau đó lặp qua tất cả các hàng trong bảng bằng vòng lặp foreach. Bên trong vòng lặp, chúng tôi vô hiệu hóa việc ngắt hàng cho mỗi hàng bằng cách đặt`RowFormat.AllowBreakAcrossPages`tài sản để`false`.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với tính năng ngắt dòng trong bảng bị tắt. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho định dạng hàng Vô hiệu hóa ngắt giữa các trang bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Tắt tính năng ngắt trang cho tất cả các hàng trong bảng.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách tắt tính năng ngắt dòng của bảng nhiều trang trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể áp dụng tính năng vô hiệu hóa này cho các bảng trong tài liệu Word của mình.