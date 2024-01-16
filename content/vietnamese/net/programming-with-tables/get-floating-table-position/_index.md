---
title: Nhận vị trí bàn nổi
linktitle: Nhận vị trí bàn nổi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách lấy vị trí của bảng nổi trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/get-floating-table-position/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách lấy vị trí của bảng nổi trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể lấy các thuộc tính định vị của bảng nổi trong tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Load tài liệu và truy cập vào bảng
Để bắt đầu Xử lý từ bằng bảng, chúng ta cần tải tài liệu chứa chúng và truy cập chúng. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn. Ngoài ra, hãy đảm bảo tài liệu chứa các bảng nổi.

## Bước 3: Lấy thuộc tính định vị bảng nổi
Tiếp theo, chúng ta sẽ lặp qua tất cả các bảng trong tài liệu và lấy các thuộc tính định vị bảng nổi. Sử dụng mã sau đây:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Nếu mảng là kiểu nổi thì hãy in các thuộc tính định vị của nó.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Ở đây chúng tôi đang sử dụng một`foreach` loop để lặp qua tất cả các mảng trong tài liệu. Chúng ta kiểm tra xem mảng có phải là kiểu float hay không bằng cách kiểm tra`TextWrapping` tài sản. Nếu vậy, chúng tôi sẽ in các thuộc tính định vị của bảng, chẳng hạn như neo ngang, neo dọc, khoảng cách ngang và dọc tuyệt đối, quyền chồng chéo, khoảng cách ngang tuyệt đối và căn chỉnh dọc tương đối.
 
### Mã nguồn mẫu cho Nhận vị trí bảng nổi bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Nếu bảng là kiểu nổi thì hãy in các thuộc tính định vị của nó.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách lấy vị trí của bảng nổi trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể nhận được các thuộc tính định vị của bảng nổi trong tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn phân tích và thao tác với các bảng nổi theo nhu cầu cụ thể của mình.