---
title: Chuyển đổi sang các ô được hợp nhất theo chiều ngang
linktitle: Chuyển đổi sang các ô được hợp nhất theo chiều ngang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi các ô của bảng thành các ô được hợp nhất theo chiều ngang trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Words cho .NET để chuyển đổi các ô trong bảng thành các ô được hợp nhất theo chiều ngang trong tài liệu Word. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể thao tác các ô bảng trong tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Load tài liệu và truy cập vào bảng
Để bắt đầu Xử lý từ bằng bảng, chúng ta cần tải tài liệu chứa nó và truy cập nó. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Truy cập vào mảng
Table table = doc.FirstSection.Body.Tables[0];
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn. Ngoài ra, hãy đảm bảo tài liệu chứa một bảng có các ô được hợp nhất theo chiều ngang.

## Bước 3: Chuyển sang ô được gộp theo chiều ngang
 Tiếp theo, chúng ta sẽ chuyển đổi các ô của bảng thành các ô được hợp nhất theo chiều ngang bằng cách sử dụng`ConvertToHorizontallyMergedCells()` phương pháp. Sử dụng mã sau đây:

```csharp
// Chuyển đổi sang các ô được hợp nhất theo chiều ngang
table. ConvertToHorizontallyMergedCells();
```

 Ở đây chúng ta chỉ gọi`ConvertToHorizontallyMergedCells()` phương thức trên mảng để thực hiện chuyển đổi.

### Mã nguồn mẫu để Chuyển đổi sang các ô được hợp nhất theo chiều ngang bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Bây giờ các ô đã hợp nhất có cờ hợp nhất thích hợp.
	table.ConvertToHorizontallyMergedCells();
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách chuyển đổi các ô trong bảng thành các ô được hợp nhất theo chiều ngang trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể thao tác các ô bảng trong tài liệu Word theo chương trình. Tính năng này cho phép bạn quản lý và sắp xếp dữ liệu của mình một cách linh hoạt và được cá nhân hóa trong bảng.