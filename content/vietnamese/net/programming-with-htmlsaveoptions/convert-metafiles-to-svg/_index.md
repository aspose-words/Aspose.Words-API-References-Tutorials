---
title: Chuyển đổi siêu tập tin sang Svg
linktitle: Chuyển đổi siêu tập tin sang Svg
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để chuyển đổi siêu tệp sang định dạng SVG khi chuyển đổi tài liệu sang HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/convert-metafiles-to-svg/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để chuyển đổi siêu tệp sang định dạng SVG bằng Aspose.Words cho .NET. Tính năng này cho phép bạn chuyển đổi siêu tệp sang định dạng SVG khi chuyển đổi tài liệu sang HTML.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Chèn ảnh SVG vào tài liệu

Ở bước này, chúng ta sẽ chèn hình ảnh SVG vào tài liệu cần chuyển đổi. Sử dụng đoạn mã sau để chèn hình ảnh SVG bằng thẻ HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an SVG image: ");
builder.InsertHtml(
	@"<svg height='210' width='500'>
	<polygon points='100,10 40,198 190,78 10,78 160,198' 
		style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
</svg> ");
```

 Mã này tạo ra một thể hiện của`Document`Và`DocumentBuilder` để xây dựng tài liệu. Nó chèn một`<svg>` thẻ chứa một`<polygon>` phần tử có các thuộc tính để xác định hình dạng và kiểu dáng của hình ảnh SVG.

## Bước 3: Đặt tùy chọn lưu HTML

Bây giờ chúng ta sẽ đặt các tùy chọn lưu HTML, chỉ định rằng siêu tệp sẽ được chuyển đổi sang định dạng SVG. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions` và bộ`MetafileFormat` ĐẾN`HtmlMetafileFormat.Svg` để chỉ định rằng siêu tệp phải được chuyển đổi sang định dạng SVG khi chuyển đổi sang HTML.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng ta sẽ chuyển đổi tài liệu sang HTML bằng cách sử dụng các tùy chọn lưu HTML được xác định trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
```

Mã này chuyển đổi tài liệu thành HTML và lưu nó vào một tệp có siêu tệp được chuyển đổi thành SVG.

### Mã nguồn mẫu cho Chuyển đổi siêu tệp sang Svg bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Write("Here is an SVG image: ");
	builder.InsertHtml(
		@"<svg height='210' width='500'>
		<polygon points='100,10 40,198 190,78 10,78 160,198' 
			style='fill:lime;stroke:purple;stroke-width:5;fill-rule:evenodd;' />
	</svg> ");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.Svg };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToSvg.html", saveOptions);
	
```
