---
title: Thiết lập trang tài liệu
linktitle: Thiết lập trang tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thiết lập bố cục tài liệu với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/document-page-setup/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để định cấu hình bố cục tài liệu với Aspose.Words cho .NET. Tính năng này cho phép bạn thiết lập chế độ bố cục, số ký tự trên mỗi dòng và số dòng trên mỗi trang.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn định cấu hình. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Thiết lập bố cục

Bây giờ hãy cấu hình bố cục tài liệu. Sử dụng đoạn mã sau để đặt chế độ bố cục, số ký tự trên mỗi dòng và số dòng trên mỗi trang:

```csharp
doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
doc.FirstSection.PageSetup.CharactersPerLine = 30;
doc.FirstSection.PageSetup.LinesPerPage = 10;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
```

Mã này đặt chế độ bố cục thành "Lưới" và sau đó chỉ định số ký tự trên mỗi dòng và số dòng trên mỗi trang.

### Mã nguồn mẫu cho Thiết lập trang tài liệu bằng Aspose.Words cho .NET


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");

	// Đặt chế độ bố cục cho một phần cho phép xác định hành vi lưới tài liệu.
	// Lưu ý rằng tab Lưới tài liệu sẽ hiển thị trong hộp thoại Thiết lập trang của MS Word
	// nếu bất kỳ ngôn ngữ Châu Á nào được xác định là ngôn ngữ chỉnh sửa.
	doc.FirstSection.PageSetup.LayoutMode = SectionLayoutMode.Grid;
	doc.FirstSection.PageSetup.CharactersPerLine = 30;
	doc.FirstSection.PageSetup.LinesPerPage = 10;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.DocumentPageSetup.docx");
   
```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách định cấu hình bố cục của tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng tùy chỉnh bố cục tài liệu của riêng mình.