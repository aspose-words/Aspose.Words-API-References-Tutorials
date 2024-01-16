---
title: Chia bảng
linktitle: Chia bảng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chia bảng trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/split-table/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách chia bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể tách bảng từ một hàng nhất định trong tài liệu Word của mình.

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

## Bước 3: Chia bảng
Tiếp theo chúng ta sẽ tách bảng từ một hàng nhất định. Sử dụng mã sau đây:

```csharp
// Truy xuất bảng đầu tiên
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Xác định đường phân chia bảng
Row row = firstTable.Rows[2];

// Tạo vùng chứa mới cho bảng phân chia
Table table = (Table)firstTable.Clone(false);

// Chèn vùng chứa sau bảng gốc
firstTable.ParentNode.InsertAfter(table, firstTable);

// Thêm đoạn đệm để duy trì khoảng cách giữa các bảng
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Di chuyển các hàng từ bảng gốc sang bảng được chia
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Ở đây chúng tôi sử dụng tài liệu để lấy bảng đầu tiên từ nút tài liệu. Sau đó, chúng tôi xác định hàng mà chúng tôi muốn chia bảng, trong ví dụ này là hàng thứ ba (chỉ mục 2). Sau đó, chúng tôi tạo một vùng chứa mới bằng cách sao chép bảng gốc rồi chèn nó vào sau bảng gốc. Chúng tôi cũng thêm một đoạn đệm để duy trì khoảng cách giữa hai bảng. Sau đó, chúng ta di chuyển các hàng từ bảng gốc sang bảng phân tách bằng vòng lặp do-while cho đến khi đến hàng được chỉ định.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng chúng ta cần lưu lại

  tài liệu được sửa đổi bằng bảng chia. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Bảng phân tách bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Chúng ta sẽ chia bàn ở hàng thứ 3 (bao gồm).
Row row = firstTable.Rows[2];
// Tạo vùng chứa mới cho bảng phân chia.
Table table = (Table) firstTable.Clone(false);
// Chèn thùng chứa sau bản gốc.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Thêm một đoạn đệm để đảm bảo các bảng tách biệt nhau.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách chia bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể dễ dàng tách bảng từ một dòng nhất định trong tài liệu Word của mình.