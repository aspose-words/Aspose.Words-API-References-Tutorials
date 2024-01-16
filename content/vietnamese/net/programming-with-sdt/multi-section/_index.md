---
title: nhiều phần
linktitle: nhiều phần
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách truy xuất và xử lý thẻ tài liệu có cấu trúc nhiều phần trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/multi-section/
---

Hướng dẫn này giải thích cách làm việc với các thẻ tài liệu có cấu trúc nhiều phần trong tài liệu Word bằng Aspose.Words cho .NET. Bạn có thể truy xuất và xử lý các thẻ phần có trong tài liệu.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu và truy xuất thẻ nhiều phần
 Tải tài liệu Word bằng cách sử dụng`Document` hàm tạo, chuyển đường dẫn đến tài liệu dưới dạng tham số. Truy xuất tất cả các nút bắt đầu phạm vi thẻ tài liệu có cấu trúc trong tài liệu bằng cách sử dụng`GetChildNodes` phương pháp.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Bước 3: Xử lý thẻ nhiều phần
Lặp lại thông qua bộ sưu tập các nút bắt đầu phạm vi thẻ tài liệu có cấu trúc. Trong ví dụ này, chúng tôi chỉ in tiêu đề của từng thẻ ra bảng điều khiển. Bạn có thể thực hiện xử lý thêm dựa trên yêu cầu của bạn.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Mã nguồn ví dụ cho Multi Mục sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Đó là nó! Bạn đã truy xuất và xử lý thành công các thẻ tài liệu có cấu trúc nhiều phần trong tài liệu Word của mình bằng Aspose.Words for .NET.