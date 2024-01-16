---
title: Xem tùy chọn
linktitle: Xem tùy chọn
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để định cấu hình các tùy chọn hiển thị tài liệu với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/view-options/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để định cấu hình các tùy chọn hiển thị với Aspose.Words cho .NET. Tính năng này cho phép bạn tùy chỉnh chế độ xem và mức thu phóng trong tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn định cấu hình các tùy chọn hiển thị. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Cấu hình các tùy chọn hiển thị

Bây giờ chúng ta sẽ cấu hình các tùy chọn hiển thị tài liệu. Sử dụng đoạn mã sau để đặt chế độ hiển thị và mức thu phóng:

```csharp
doc.ViewOptions.ViewType = ViewType.PageLayout;
doc.ViewOptions.ZoomPercent = 50;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
```

Mã này đặt chế độ xem thành "PageLayout" và mức thu phóng thành 50%.

### Mã nguồn ví dụ cho Tùy chọn xem bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	doc.ViewOptions.ViewType = ViewType.PageLayout;
	doc.ViewOptions.ZoomPercent = 50;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.ViewOptions.docx");
    
```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách định cấu hình các tùy chọn hiển thị tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng tùy chỉnh cách hiển thị tài liệu của riêng mình.