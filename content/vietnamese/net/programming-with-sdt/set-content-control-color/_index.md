---
title: Đặt màu kiểm soát nội dung
linktitle: Đặt màu kiểm soát nội dung
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt màu của điều khiển nội dung trong tài liệu Word bằng Aspose.Words cho .NET, tùy chỉnh giao diện của nó.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/set-content-control-color/
---

Hướng dẫn này giải thích cách đặt màu của điều khiển nội dung trong tài liệu Word bằng Aspose.Words cho .NET. Bạn có thể tùy chỉnh giao diện của các điều khiển nội dung bằng cách thay đổi màu sắc của chúng.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu và truy xuất Kiểm soát nội dung
 Tải tài liệu Word bằng cách sử dụng`Document`hàm tạo, chuyển đường dẫn đến tài liệu dưới dạng tham số. Truy xuất điều khiển nội dung mong muốn từ tài liệu. Trong ví dụ này, chúng tôi giả định rằng điều khiển nội dung là thẻ tài liệu có cấu trúc đầu tiên trong tài liệu.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Bước 3: Đặt màu điều khiển nội dung
 Đặt màu của điều khiển nội dung bằng cách gán một`Color` giá trị để`Color` thuộc tính của thẻ tài liệu có cấu trúc. Trong ví dụ này, chúng tôi đặt màu thành màu đỏ.

```csharp
sdt.Color = Color.Red;
```

## Bước 4: Lưu tài liệu
 Lưu tài liệu đã sửa đổi vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Mã nguồn mẫu cho Đặt màu kiểm soát nội dung bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Đó là nó! Bạn đã đặt thành công màu của điều khiển nội dung trong tài liệu Word của mình bằng Aspose.Words for .NET.