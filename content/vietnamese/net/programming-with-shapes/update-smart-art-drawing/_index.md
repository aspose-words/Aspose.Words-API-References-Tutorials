---
title: Cập nhật bản vẽ nghệ thuật thông minh
linktitle: Cập nhật bản vẽ nghệ thuật thông minh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách cập nhật bản vẽ Smart Art trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/update-smart-art-drawing/
---

Hướng dẫn này giải thích cách cập nhật bản vẽ Smart Art trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách lặp qua các hình dạng trong tài liệu và kiểm tra xem chúng có Smart Art hay không, bạn có thể cập nhật bản vẽ Smart Art để phản ánh bất kỳ thay đổi nào được thực hiện đối với dữ liệu của nó.

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
 Tải tài liệu Word có chứa bản vẽ Smart Art bằng cách sử dụng`Document` hàm tạo lớp.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Bước 3: Cập nhật bản vẽ nghệ thuật thông minh
 Lặp lại các hình dạng trong tài liệu bằng cách sử dụng`GetChildNodes` phương pháp với`NodeType.Shape` thông số. Kiểm tra xem mỗi hình có Smart Art hay không bằng cách sử dụng`HasSmartArt` thuộc tính và nếu đúng, hãy gọi`UpdateSmartArtDrawing` phương pháp cập nhật bản vẽ Smart Art.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Mã nguồn mẫu cho Cập nhật bản vẽ nghệ thuật thông minh bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Đó là nó! Bạn đã cập nhật thành công bản vẽ Smart Art trong tài liệu Word của mình bằng Aspose.Words for .NET.