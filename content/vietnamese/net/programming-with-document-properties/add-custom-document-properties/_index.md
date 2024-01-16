---
title: Thêm thuộc tính tài liệu tùy chỉnh
linktitle: Thêm thuộc tính tài liệu tùy chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thêm thuộc tính tùy chỉnh vào tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/add-custom-document-properties/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để thêm thuộc tính tùy chỉnh vào tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn thêm thông tin tùy chỉnh vào tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn thêm thuộc tính tùy chỉnh. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Thêm thuộc tính tùy chỉnh

Bây giờ hãy thêm các thuộc tính tùy chỉnh vào tài liệu. Sử dụng đoạn mã sau để thêm các thuộc tính:

```csharp
CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;

if (customDocumentProperties["Authorized"] != null) return;

customDocumentProperties.Add("Authorized", true);
customDocumentProperties.Add("Authorized By", "John Smith");
customDocumentProperties.Add("Authorized Date", DateTime.Today);
customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
customDocumentProperties.Add("Authorized Amount", 123.45);
```

Mã này trước tiên sẽ kiểm tra xem thuộc tính "Được ủy quyền" đã tồn tại trong thuộc tính tùy chỉnh hay chưa. Nếu nó tồn tại, quá trình bị gián đoạn. Nếu không, các thuộc tính tùy chỉnh sẽ được thêm vào tài liệu.

### Mã nguồn mẫu cho Thêm thuộc tính tài liệu tùy chỉnh bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");

	CustomDocumentProperties customDocumentProperties = doc.CustomDocumentProperties;
	
	if (customDocumentProperties["Authorized"] != null) return;
	
	customDocumentProperties.Add("Authorized", true);
	customDocumentProperties.Add("Authorized By", "John Smith");
	customDocumentProperties.Add("Authorized Date", DateTime.Today);
	customDocumentProperties.Add("Authorized Revision", doc.BuiltInDocumentProperties.RevisionNumber);
	customDocumentProperties.Add("Authorized Amount", 123.45);

```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách thêm thuộc tính tùy chỉnh vào tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng thêm các thuộc tính tùy chỉnh của riêng mình vào tài liệu của mình.