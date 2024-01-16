---
title: Xuất Url Cid Cho Tài Nguyên Mhtml
linktitle: Xuất Url Cid Cho Tài Nguyên Mhtml
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xuất URL CID của tài nguyên MHTML khi lưu tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/export-cid-urls-for-mhtml-resources/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để xuất URL CID cho tài nguyên MHTML bằng Aspose.Words cho .NET. Tính năng này cho phép bạn xuất URL CID của tài nguyên MHTML khi lưu tài liệu ở định dạng MHTML.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Ở bước này, chúng ta sẽ tải tài liệu để xuất. Sử dụng đoạn mã sau để tải tài liệu từ một thư mục được chỉ định:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Content-ID.docx");
```

 Mã này tạo ra một thể hiện của`Document` bằng cách tải tài liệu từ thư mục được chỉ định.

## Bước 3: Định cấu hình tùy chọn sao lưu HTML

Bây giờ chúng tôi sẽ định cấu hình các tùy chọn lưu HTML để xuất URL CID của tài nguyên MHTML. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
{
PrettyFormat = true,
ExportCidUrlsForMhtmlResources = true
};
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions` với định dạng lưu được đặt thành MHTML. Nó cũng cho phép xuất các URL CID của tài nguyên MHTML bằng cách cài đặt`ExportCidUrlsForMhtmlResources` ĐẾN`true`.

## Bước 4: Chuyển đổi và lưu tài liệu sang MHTML

Cuối cùng, chúng tôi sẽ chuyển đổi tài liệu sang MHTML bằng cách sử dụng các tùy chọn lưu HTML được định cấu hình trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);
```

Mã này chuyển đổi tài liệu thành MHTML và lưu nó vào một tệp có URL CID của tài nguyên MHTML đã xuất.

### Mã nguồn mẫu cho Xuất Url Cid cho Tài nguyên Mhtml bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Content-ID.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Mhtml)
	{
		PrettyFormat = true, ExportCidUrlsForMhtmlResources = true
	};

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportCidUrlsForMhtmlResources.mhtml", saveOptions);

```

 Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu trong thư mục`dataDir` Biến đổi.

Bây giờ bạn đã học cách xuất URL CID của tài nguyên MHTML khi lưu tài liệu ở định dạng MHTML bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng quản lý URL CID trong tài liệu MHTML đã xuất của mình.

