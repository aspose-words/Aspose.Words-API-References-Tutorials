---
title: Đặt thiết lập trang và định dạng phần
linktitle: Đặt thiết lập trang và định dạng phần
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thiết lập bố cục và định dạng phần của tài liệu bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-options-and-settings/set-page-setup-and-section-formatting/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để thiết lập bố cục và định dạng phần bằng Aspose.Words cho .NET. Tính năng này cho phép bạn đặt hướng trang, lề và kích thước giấy.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tạo tài liệu

Ở bước này, chúng ta sẽ tạo một tài liệu mới. Sử dụng đoạn mã sau để tạo tài liệu và khởi tạo hàm tạo:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục mà bạn muốn lưu tài liệu.

## Bước 3: Thiết lập bố cục và lưu tài liệu

Bây giờ hãy cấu hình bố cục tài liệu. Sử dụng đoạn mã sau để đặt hướng, lề và khổ giấy:

```csharp
builder.PageSetup.Orientation = Orientation.Landscape;
builder.PageSetup.LeftMargin = 50;
builder.PageSetup.PaperSize = PaperSize.Paper10x14;

doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
```

Mã này sẽ đặt hướng trang thành ngang, lề trái thành 50 và khổ giấy thành 10x14.

### Mã nguồn ví dụ cho Thiết lập trang và định dạng phần bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.PageSetup.Orientation = Orientation.Landscape;
	builder.PageSetup.LeftMargin = 50;
	builder.PageSetup.PaperSize = PaperSize.Paper10x14;

	doc.Save(dataDir + "WorkingWithDocumentOptionsAndSettings.SetPageSetupAndSectionFormatting.docx");
  
```

 Đảm bảo chỉ định đường dẫn chính xác đến thư mục mà bạn muốn lưu tài liệu vào`dataDir` Biến đổi.

Bây giờ bạn đã học cách định cấu hình bố cục và định dạng phần của tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng tùy chỉnh bố cục và định dạng tài liệu của riêng mình.