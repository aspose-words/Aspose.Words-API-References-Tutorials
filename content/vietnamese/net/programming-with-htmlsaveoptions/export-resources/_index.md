---
title: Xuất khẩu tài nguyên
linktitle: Xuất khẩu tài nguyên
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xuất tài nguyên tài liệu khi lưu dưới dạng HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/export-resources/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để xuất tài nguyên tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn xuất các tài nguyên, chẳng hạn như phông chữ, dưới dạng tệp bên ngoài khi lưu tài liệu ở định dạng HTML.

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

Bây giờ chúng tôi sẽ định cấu hình các tùy chọn lưu HTML để xuất tài nguyên tài liệu. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
CssStyleSheetType = CssStyleSheetType.External,
ExportFontResources=true,
ResourceFolder = ArtifactsDir + "Resources",
ResourceFolderAlias = "http://example.com/resource"
};
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions` và đặt các tùy chọn sau:

- `CssStyleSheetType` được đặt thành`CssStyleSheetType.External`để xuất biểu định kiểu CSS sang tệp bên ngoài.
- `ExportFontResources` được đặt thành`true` để xuất tài nguyên phông chữ.
- `ResourceFolder` chỉ định thư mục đích nơi tài nguyên sẽ được lưu.
- `ResourceFolderAlias` chỉ định bí danh URL sẽ được sử dụng để truy cập tài nguyên.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng tôi sẽ chuyển đổi tài liệu sang HTML bằng các tùy chọn lưu HTML được định cấu hình trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Mã này chuyển đổi tài liệu sang HTML và lưu tài nguyên vào thư mục được chỉ định, sử dụng bí danh URL được chỉ định.

### Mã nguồn ví dụ về Xuất tài nguyên bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External,
		ExportFontResources = true,
		ResourceFolder = ArtifactsDir + "Resources",
		ResourceFolderAlias = "http://example.com/resource"
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
  
```

 Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu trong thư mục`dataDir` Biến đổi.