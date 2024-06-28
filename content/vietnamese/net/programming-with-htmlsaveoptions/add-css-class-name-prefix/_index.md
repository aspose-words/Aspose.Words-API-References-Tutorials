---
title: Thêm tiền tố tên lớp Css
linktitle: Thêm tiền tố tên lớp Css
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thêm tiền tố tên lớp CSS khi chuyển đổi tài liệu sang HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để thêm tiền tố tên lớp CSS với Aspose.Words cho .NET. Tính năng này cho phép bạn thêm tiền tố tùy chỉnh vào tên lớp CSS được tạo khi chuyển đổi tài liệu sang HTML.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word mà chúng tôi muốn chuyển đổi sang HTML. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Đặt tùy chọn lưu HTML

Bây giờ, hãy đặt các tùy chọn lưu HTML, bao gồm loại biểu định kiểu CSS và tiền tố tên lớp CSS. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
     CssStyleSheetType = CssStyleSheetType.External,
     CssClassNamePrefix = "pfx_"
};
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions` và bộ`CssStyleSheetType` ĐẾN`CssStyleSheetType.External`để tạo một biểu định kiểu CSS bên ngoài và`CssClassNamePrefix` ĐẾN`"pfx_"` đến tiền tố`"pfx_"` để đặt tên cho các lớp CSS.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng ta sẽ chuyển đổi tài liệu sang HTML bằng cách sử dụng các tùy chọn lưu HTML được xác định trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

Mã này chuyển đổi tài liệu thành HTML và lưu nó vào một tệp có thêm tiền tố tên lớp CSS.

### Mã nguồn ví dụ cho Thêm tiền tố tên lớp Css bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions
	{
		CssStyleSheetType = CssStyleSheetType.External, CssClassNamePrefix = "pfx_"
	};
	
	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);

```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách thêm tiền tố tên lớp CSS khi chuyển đổi tài liệu sang HTML bằng Aspose.Words cho .NET. Làm theo bước hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể tùy chỉnh tên lớp CSS trong tài liệu HTML đã chuyển đổi của mình.