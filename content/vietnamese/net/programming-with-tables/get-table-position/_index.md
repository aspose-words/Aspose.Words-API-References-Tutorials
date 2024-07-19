---
title: Nhận vị trí bảng
linktitle: Nhận vị trí bảng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách lấy vị trí của bảng trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/get-table-position/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách lấy vị trí của bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể lấy các thuộc tính định vị bảng trong tài liệu Word của mình theo chương trình.

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

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn. Ngoài ra, hãy đảm bảo tài liệu chứa bảng có vị trí bạn muốn nhận.

## Bước 3: Lấy thuộc tính định vị mảng
Tiếp theo, chúng ta sẽ kiểm tra kiểu định vị của mảng và lấy các thuộc tính định vị thích hợp. Sử dụng mã sau đây:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Ở đây chúng ta sử dụng một điều kiện để kiểm tra xem mảng có phải là kiểu float hay không. Nếu vậy, chúng tôi in`RelativeHorizontalAlignment`Và`RelativeVerticalAlignment` Properties để có được sự liên kết theo chiều ngang và chiều dọc tương đối của bảng. Nếu không, chúng tôi in`Alignment` thuộc tính để có được sự liên kết mảng.

### Mã nguồn mẫu cho Nhận vị trí bảng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách lấy vị trí của bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể nhận được các thuộc tính định vị bảng trong tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn phân tích và thao tác các mảng theo vị trí cụ thể của chúng.