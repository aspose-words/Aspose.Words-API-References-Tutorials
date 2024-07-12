---
title: Chuyển đổi siêu tập tin sang Emf hoặc Wmf
linktitle: Chuyển đổi siêu tập tin sang Emf hoặc Wmf
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để chuyển đổi siêu tệp sang định dạng EMF hoặc WMF khi chuyển đổi tài liệu sang HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/convert-metafiles-to-emf-or-wmf/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để chuyển đổi siêu tệp sang định dạng EMF hoặc WMF bằng Aspose.Words cho .NET. Tính năng này cho phép bạn chuyển đổi hình ảnh ở định dạng siêu tệp sang các định dạng tương thích hơn như EMF hoặc WMF khi chuyển đổi tài liệu sang HTML.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Chèn hình ảnh vào tài liệu

Ở bước này, chúng ta sẽ chèn hình ảnh vào tài liệu cần chuyển đổi. Sử dụng mã sau để chèn hình ảnh từ nguồn dữ liệu bằng thẻ HTML:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Here is an image as is: ");
builder.InsertHtml(
	@"<img src=""data:image/png;base64,
		iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
		C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
		AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
		REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
		ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
		vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");
```

 Mã này tạo ra một thể hiện của`Document`Và`DocumentBuilder` để xây dựng tài liệu. Nó chèn một`<img>` gắn thẻ vào tài liệu bằng hình ảnh được mã hóa base64.

## Bước 3: Đặt tùy chọn lưu HTML

Bây giờ chúng ta sẽ đặt các tùy chọn lưu HTML, bao gồm định dạng siêu tệp để sử dụng cho hình ảnh. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions` và bộ`MetafileFormat` ĐẾN`HtmlMetafileFormat.EmfOrWmf` để chỉ định rằng siêu tệp phải được chuyển đổi sang định dạng EMF hoặc WMF khi chuyển đổi sang HTML.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng tôi sẽ chuyển đổi tài liệu sang HTML bằng cách sử dụng các tùy chọn lưu HTML được xác định trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);
```

Mã này chuyển đổi tài liệu thành HTML và lưu nó vào một tệp có siêu tệp được chuyển đổi ở định dạng EMF hoặc WMF tùy thuộc vào bộ tùy chọn lưu.

### Mã nguồn ví dụ để Chuyển đổi siêu tệp sang Emf hoặc Wmf bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Here is an image as is: ");
	builder.InsertHtml(
		@"<img src=""data:image/png;base64,
			iVBORw0KGgoAAAANSUhEUgAAAAoAAAAKCAYAAACNMs+9AAAABGdBTUEAALGP
			C/xhBQAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9YGARc5KB0XV+IA
			AAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAF1J
			REFUGNO9zL0NglAAxPEfdLTs4BZM4DIO4C7OwQg2JoQ9LE1exdlYvBBeZ7jq
			ch9//q1uH4TLzw4d6+ErXMMcXuHWxId3KOETnnXXV6MJpcq2MLaI97CER3N0
			vr4MkhoXe0rZigAAAABJRU5ErkJggg=="" alt=""Red dot"" />");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { MetafileFormat = HtmlMetafileFormat.EmfOrWmf };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ConvertMetafilesToEmfOrWmf.html", saveOptions);

```

 Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu trong thư mục`dataDir` Biến đổi.

Bây giờ bạn đã học cách chuyển đổi siêu tệp sang định dạng EMF hoặc WMF khi chuyển đổi tài liệu sang HTML bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng quản lý siêu tệp trong tài liệu HTML đã chuyển đổi của mình.