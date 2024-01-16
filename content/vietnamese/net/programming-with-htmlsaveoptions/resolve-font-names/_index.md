---
title: Giải quyết tên phông chữ
linktitle: Giải quyết tên phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để giải quyết tên phông chữ bị thiếu khi chuyển đổi sang HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/resolve-font-names/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để giải quyết các tên phông chữ bị thiếu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn tự động giải quyết các tên phông chữ bị thiếu khi chuyển đổi tài liệu sang HTML.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Ở bước này, chúng ta sẽ tải tài liệu cần xử lý. Sử dụng đoạn mã sau để tải tài liệu từ một thư mục được chỉ định:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Missing font.docx");
```

 Mã này tạo ra một thể hiện của`Document` bằng cách tải tài liệu từ thư mục được chỉ định.

## Bước 3: Định cấu hình tùy chọn sao lưu HTML

Bây giờ chúng tôi sẽ định cấu hình các tùy chọn lưu HTML để giải quyết các tên phông chữ bị thiếu trong quá trình chuyển đổi. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
PrettyFormat = true,
ResolveFontNames=true
};
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions`và thiết lập`ResolveFontNames` tùy chọn để`true`để giải quyết các tên phông chữ bị thiếu khi chuyển đổi sang HTML. Ngoài ra,`PrettyFormat` tùy chọn được đặt thành`true` để có được mã HTML được định dạng độc đáo.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng tôi sẽ chuyển đổi tài liệu sang HTML bằng các tùy chọn lưu HTML được định cấu hình trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);
```

Mã này chuyển đổi tài liệu sang HTML bằng cách tự động giải quyết các tên phông chữ bị thiếu và lưu tệp HTML đã chuyển đổi vào thư mục được chỉ định.

### Mã nguồn ví dụ để phân giải tên phông chữ bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Missing font.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
	{
		PrettyFormat = true, ResolveFontNames = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ResolveFontNames.html", saveOptions);

```

 Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu trong thư mục`dataDir` Biến đổi.