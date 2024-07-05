---
title: Giữ bàn cùng nhau
linktitle: Giữ bàn cùng nhau
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách giữ các bảng lại với nhau trong tài liệu Word bằng Aspose.Words dành cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/keep-table-together/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách giữ các bảng lại với nhau trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể giữ nguyên bảng mà không bị chia thành nhiều trang trong tài liệu Word của mình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Load tài liệu và lấy bảng
Để bắt đầu Xử lý từ bằng bảng, chúng ta cần tải tài liệu và tìm nạp bảng mà chúng ta muốn giữ cùng nhau. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Truy xuất bảng
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Kích hoạt tùy chọn "KeepWithNext"
Để giữ bảng lại với nhau và ngăn bảng bị chia thành nhiều trang, chúng ta cần bật tùy chọn "KeepWithNext" cho từng đoạn trong bảng ngoại trừ các đoạn cuối của hàng cuối cùng của bảng. Sử dụng mã sau đây:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Ở đây, chúng tôi lặp qua từng ô trong bảng và bật tùy chọn "KeepWithNext" cho từng đoạn trong ô ngoại trừ các đoạn cuối cùng của hàng cuối cùng trong bảng.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với bảng được giữ cùng nhau. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Keep Table Together bằng Aspose.Words for .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Chúng ta cần bật KeepWithNext cho mỗi đoạn trong bảng để giữ cho đoạn văn đó không bị vỡ trên một trang,
	// ngoại trừ các đoạn cuối cùng ở hàng cuối cùng của bảng.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách giữ các bảng lại với nhau trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể giữ nguyên bảng và ngăn bảng bị chia thành nhiều trang trong tài liệu của mình. Tính năng này cho phép bạn kiểm soát nhiều hơn về hình thức và bố cục của các bảng trong tài liệu của mình.