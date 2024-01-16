---
title: Phát hiện hình dạng nghệ thuật thông minh
linktitle: Phát hiện hình dạng nghệ thuật thông minh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách phát hiện các hình dạng Nghệ thuật thông minh trong tài liệu Word bằng Aspose.Words cho .NET, xác định các biểu diễn đồ họa.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/detect-smart-art-shape/
---

Hướng dẫn này giải thích cách phát hiện các hình dạng Smart Art trong tài liệu Word bằng Aspose.Words for .NET. Hình dạng Smart Art là các hình thức biểu diễn đồ họa được sử dụng để trình bày thông tin và ý tưởng một cách trực quan.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu
 Tải tài liệu Word bằng cách sử dụng`Document` hàm tạo, chuyển đường dẫn đến tài liệu dưới dạng tham số.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Bước 3: Phát hiện hình dạng nghệ thuật thông minh
 Lặp lại qua các nút con thuộc loại`Shape` trong tài liệu bằng cách sử dụng`GetChildNodes`phương pháp. Kiểm tra xem mỗi hình có Smart Art hay không bằng cách sử dụng`HasSmart Art` tài sản.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Bước 4: Xuất kết quả
In số lượng hình dạng bằng Smart Art được phát hiện trong tài liệu.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Mã nguồn mẫu cho Phát hiện hình dạng nghệ thuật thông minh bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Đó là nó! Bạn đã phát hiện thành công các hình dạng Smart Art trong tài liệu Word của mình bằng Aspose.Words for .NET.