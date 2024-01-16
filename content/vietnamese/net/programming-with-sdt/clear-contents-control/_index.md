---
title: Kiểm soát nội dung rõ ràng
linktitle: Kiểm soát nội dung rõ ràng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xóa nội dung của điều khiển trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/clear-contents-control/
---

Hướng dẫn này trình bày cách xóa nội dung của SDT trong tài liệu Word bằng Aspose.Words cho .NET. Việc xóa nội dung của SDT sẽ xóa mọi văn bản hoặc nút con trong phần kiểm soát nội dung.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu và lấy StructuredDocumentTag
 Tải tài liệu Word bằng cách sử dụng`Document` hàm tạo, chuyển đường dẫn đến tài liệu dưới dạng tham số. Sau đó, truy xuất mong muốn`StructuredDocumentTag` từ tài liệu. Trong ví dụ này, chúng tôi giả định rằng SDT là nút con đầu tiên trong tài liệu.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Bước 3: Xóa nội dung của StructuredDocumentTag
 Xóa nội dung của SDT bằng cách sử dụng`Clear` phương pháp. Thao tác này sẽ xóa mọi nút văn bản hoặc nút con trong phần kiểm soát nội dung.

```csharp
sdt.Clear();
```

## Bước 4: Lưu tài liệu
 Lưu tài liệu đã sửa đổi bằng cách sử dụng`Save`phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Mã nguồn mẫu cho Kiểm soát nội dung rõ ràng bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Đó là nó! Bạn đã xóa thành công nội dung của StructuredDocumentTag trong tài liệu Word của mình bằng Aspose.Words for .NET.