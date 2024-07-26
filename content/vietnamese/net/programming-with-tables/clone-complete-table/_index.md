---
title: Sao chép bảng hoàn chỉnh
linktitle: Sao chép bảng hoàn chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sao chép toàn bộ bảng vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/clone-complete-table/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Words cho .NET để sao chép toàn bộ bảng vào tài liệu Word. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể sao chép các bảng vào tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Load tài liệu và truy cập vào bảng
Để bắt đầu Xử lý từ bằng bảng, chúng ta cần tải tài liệu chứa nó và truy cập nó. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Tables.docx");

// Truy cập vào mảng
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Sao chép toàn bộ mảng
Tiếp theo, chúng ta sẽ sao chép toàn bộ bảng và chèn nó vào tài liệu sau bản gốc. Sử dụng mã sau đây:

```csharp
// Sao chép mảng
Table tableClone = (Table)table.Clone(true);

// Chèn bảng nhân bản vào tài liệu sau bản gốc
table.ParentNode.InsertAfter(tableClone, table);

// Chèn một đoạn trống giữa hai bảng
// Nếu không, chúng sẽ được kết hợp thành một khi lưu (điều này là do xác thực tài liệu)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Ở đây chúng tôi đang sử dụng`Clone` phương pháp để tạo một bản sao hoàn chỉnh của mảng. Sau đó chúng tôi sử dụng`InsertAfter` để chèn bảng nhân bản vào tài liệu, sau bảng gốc. Chúng ta cũng thêm một đoạn trống giữa hai bảng để tránh bị hợp nhất khi lưu.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi bằng bảng nhân bản. Sử dụng mã sau đây:

```csharp
// Lưu tài liệu đã sửa đổi
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.
  
### Mã nguồn mẫu cho Bảng sao chép hoàn chỉnh bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Sao chép bảng và chèn nó vào tài liệu sau bản gốc.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Chèn một đoạn trống giữa hai bảng,
	// nếu không chúng sẽ được kết hợp thành một khi lưu, việc này liên quan đến việc xác thực tài liệu.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách sao chép toàn bộ bảng vào tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể sao chép các bảng trong tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn thực hiện các thao tác nâng cao trên mảng để phù hợp với nhu cầu cụ thể của mình.