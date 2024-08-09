---
title: Định dạng hàng Tắt ngắt trên các trang
linktitle: Định dạng hàng Tắt ngắt trên các trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tắt ngắt hàng trên các trang trong tài liệu Word bằng Aspose.Words for .NET để duy trì khả năng đọc và định dạng bảng.
type: docs
weight: 10
url: /vi/net/programming-with-tables/row-format-disable-break-across-pages/
---
## Giới thiệu

Khi làm việc với các bảng trong tài liệu Word, bạn có thể muốn đảm bảo rằng các hàng không bị ngắt giữa các trang, điều này có thể cần thiết để duy trì khả năng đọc và định dạng tài liệu của bạn. Aspose.Words for .NET cung cấp một cách dễ dàng để vô hiệu hóa ngắt hàng trên các trang.

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình vô hiệu hóa ngắt hàng trên các trang trong tài liệu Word bằng Aspose.Words cho .NET.

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Đã cài đặt thư viện Aspose.Words cho .NET.
- Tài liệu Word có bảng trải dài trên nhiều trang.

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cần thiết trong dự án của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
```

## Bước 1: Tải tài liệu

Tải tài liệu chứa bảng trải dài trên nhiều trang.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

## Bước 2: Truy cập bảng

Truy cập bảng đầu tiên trong tài liệu. Điều này giả định rằng bảng bạn muốn sửa đổi là bảng đầu tiên trong tài liệu.

```csharp
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
```

## Bước 3: Vô hiệu hóa tính năng ngắt trang cho tất cả các hàng

 Lặp qua từng hàng trong bảng và đặt`AllowBreakAcrossPages`tài sản để`false`. Điều này đảm bảo rằng các hàng sẽ không bị ngắt giữa các trang.

```csharp
// Tắt tính năng ngắt trang cho tất cả các hàng trong bảng.
foreach (Row row in table.Rows)
    row.RowFormat.AllowBreakAcrossPages = false;
```

## Bước 4: Lưu tài liệu

Lưu tài liệu đã sửa đổi vào thư mục được chỉ định của bạn.

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách tắt ngắt hàng trên các trang trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được nêu ở trên, bạn có thể đảm bảo rằng các hàng trong bảng vẫn còn nguyên và không bị phân chia giữa các trang, duy trì khả năng đọc và định dạng của tài liệu.

## Câu hỏi thường gặp

### Tôi có thể tắt tính năng ngắt hàng trên các trang cho một hàng cụ thể thay vì tất cả các hàng không?  
 Có, bạn có thể vô hiệu hóa ngắt hàng cho các hàng cụ thể bằng cách truy cập vào hàng mong muốn và đặt nó`AllowBreakAcrossPages`tài sản để`false`.

### Phương pháp này có hoạt động với các bảng có ô được hợp nhất không?  
 Có, phương pháp này áp dụng cho các bảng có ô được hợp nhất. tài sản`AllowBreakAcrossPages` áp dụng cho toàn bộ hàng, bất kể việc hợp nhất ô.

### Phương pháp này có hoạt động không nếu bảng được lồng bên trong một bảng khác?  
Có, bạn có thể truy cập và sửa đổi các bảng lồng nhau theo cách tương tự. Đảm bảo bạn tham chiếu chính xác bảng lồng nhau theo chỉ mục của nó hoặc các thuộc tính khác.

### Làm cách nào để kiểm tra xem một hàng có cho phép ngắt giữa các trang hay không?  
 Bạn có thể kiểm tra xem một hàng có cho phép ngắt giữa các trang hay không bằng cách truy cập vào`AllowBreakAcrossPages` tài sản của`RowFormat` và kiểm tra giá trị của nó.

### Có cách nào để áp dụng cài đặt này cho tất cả các bảng trong tài liệu không?  
Có, bạn có thể lặp qua tất cả các bảng trong tài liệu và áp dụng cài đặt này cho từng bảng.