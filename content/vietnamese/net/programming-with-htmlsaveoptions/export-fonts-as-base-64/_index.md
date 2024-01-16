---
title: Xuất phông chữ dưới dạng cơ sở 64
linktitle: Xuất phông chữ dưới dạng cơ sở 64
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xuất phông chữ cơ sở 64 khi lưu tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/export-fonts-as-base-64/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để xuất phông chữ cơ sở 64 bằng Aspose.Words cho .NET. Tính năng này cho phép bạn xuất phông chữ dưới dạng dữ liệu cơ sở 64 khi lưu tài liệu ở định dạng HTML.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Ở bước này, chúng ta sẽ tải tài liệu để xuất. Sử dụng đoạn mã sau để tải tài liệu từ một thư mục được chỉ định:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Mã này tạo ra một thể hiện của`Document` bằng cách tải tài liệu từ thư mục được chỉ định.

## Bước 3: Định cấu hình tùy chọn sao lưu HTML

Bây giờ chúng ta sẽ định cấu hình các tùy chọn lưu HTML để xuất phông chữ cơ sở 64. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions` và bộ`ExportFontsAsBase64` ĐẾN`true` để chỉ định rằng phông chữ phải được xuất dưới dạng dữ liệu cơ sở 64 khi lưu dưới dạng HTML.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng tôi sẽ chuyển đổi tài liệu sang HTML bằng các tùy chọn lưu HTML được định cấu hình trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);
```

Mã này chuyển đổi tài liệu thành HTML và lưu nó vào một tệp có phông chữ được xuất dưới dạng dữ liệu cơ sở 64.

### Mã nguồn mẫu để xuất phông chữ dưới dạng cơ sở 64 bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportFontsAsBase64 = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportFontsAsBase64.html", saveOptions);

```

 Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu trong thư mục`dataDir` Biến đổi.

Bây giờ bạn đã học cách xuất phông chữ cơ sở 64 khi lưu tài liệu dưới dạng HTML bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng xuất phông chữ một cách an toàn và được nhúng vào tài liệu HTML của mình.