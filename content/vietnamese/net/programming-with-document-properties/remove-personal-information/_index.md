---
title: Xóa thông tin cá nhân
linktitle: Xóa thông tin cá nhân
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xóa thông tin cá nhân khỏi tài liệu bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/remove-personal-information/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để xóa thông tin cá nhân khỏi tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn xóa thông tin cá nhân nhạy cảm khỏi tài liệu, chẳng hạn như dữ liệu nhận dạng tác giả.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải lên tài liệu Word mà chúng tôi muốn xóa thông tin cá nhân. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Xóa thông tin cá nhân

 Bây giờ chúng tôi sẽ cho phép xóa thông tin cá nhân bằng cách đặt`RemovePersonalInformation`tài sản để`true`. Sử dụng mã sau đây:

```csharp
doc.RemovePersonalInformation = true;
```

Mã này kích hoạt việc xóa thông tin cá nhân trong tài liệu.

## Bước 4: Lưu tài liệu

Cuối cùng, chúng tôi sẽ lưu tài liệu đã xóa thông tin cá nhân. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
```

Mã này lưu tài liệu đã xóa thông tin cá nhân vào một tệp mới.

### Mã nguồn mẫu cho Xóa thông tin cá nhân bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx") { RemovePersonalInformation = true };

	doc.Save(dataDir + "DocumentPropertiesAndVariables.RemovePersonalInformation.docx");
	
```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách xóa thông tin cá nhân khỏi tài liệu bằng Aspose.Words for .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng xóa thông tin nhạy cảm khỏi tài liệu của riêng mình.