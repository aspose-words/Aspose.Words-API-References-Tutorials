---
title: Truy xuất loại chiều rộng ưa thích
linktitle: Truy xuất loại chiều rộng ưa thích
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách truy xuất loại và giá trị độ rộng ưa thích của một ô trong bảng Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/retrieve-preferred-width-type/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách truy xuất loại chiều rộng ưa thích và giá trị của nó từ một ô bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Ở cuối hướng dẫn này, bạn sẽ có thể truy xuất loại chiều rộng ưa thích (tuyệt đối, tương đối hoặc tự động) và giá trị của nó cho một ô cụ thể trong bảng tài liệu Word của bạn.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tải tài liệu
Để bắt đầu Xử lý văn bản với tài liệu, hãy làm theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Tables.docx");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn và cung cấp tên tệp chính xác.

## Bước 3: Truy xuất loại và giá trị chiều rộng ưa thích
Tiếp theo, chúng tôi sẽ truy xuất loại chiều rộng ưa thích và giá trị của nó cho một ô bảng cụ thể. Sử dụng mã sau đây:

```csharp
// Truy xuất bảng
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Kích hoạt điều chỉnh bảng tự động
table. AllowAutoFit = true;

// Lấy ô đầu tiên của hàng đầu tiên
Cell firstCell = table.FirstRow.FirstCell;

// Truy xuất loại chiều rộng ưa thích và giá trị của nó
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

Ở đây chúng tôi sử dụng tài liệu để tìm nạp bảng đầu tiên, sau đó chúng tôi kích hoạt bảng tự động phù hợp với`AllowAutoFit` tài sản. Sau đó, chúng tôi lấy ô đầu tiên của hàng đầu tiên của bảng. Từ ô này, chúng ta có thể truy xuất loại chiều rộng ưa thích bằng`PreferredWidth.Type` tài sản và giá trị của nó bằng`PreferredWidth.Value` tài sản.

### Mã nguồn mẫu cho Truy xuất Loại chiều rộng ưa thích bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách truy xuất loại chiều rộng ưa thích và giá trị của nó từ một ô bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể truy xuất thông tin này cho các ô cụ thể trong bảng tài liệu Word của mình.