---
title: Xóa thuộc tính tài liệu tùy chỉnh
linktitle: Xóa thuộc tính tài liệu tùy chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xóa thuộc tính tùy chỉnh khỏi tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/remove-custom-document-properties/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để xóa các thuộc tính tùy chỉnh khỏi tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn xóa một thuộc tính tùy chỉnh cụ thể khỏi tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn xóa các thuộc tính tùy chỉnh. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Xóa thuộc tính tùy chỉnh

Bây giờ hãy xóa một thuộc tính tùy chỉnh cụ thể khỏi tài liệu. Sử dụng mã sau đây:

```csharp
doc.CustomDocumentProperties.Remove("Authorized Date");
```

Mã này xóa thuộc tính tùy chỉnh "Ngày được ủy quyền" khỏi tài liệu. Bạn có thể thay thế "Ngày ủy quyền" bằng tên của thuộc tính tùy chỉnh mà bạn muốn xóa.

### Mã nguồn mẫu cho Xóa thuộc tính tài liệu tùy chỉnh bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	doc.CustomDocumentProperties.Remove("Authorized Date");
	
```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách xóa thuộc tính tùy chỉnh khỏi tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng xóa các thuộc tính tùy chỉnh khỏi tài liệu của riêng mình.