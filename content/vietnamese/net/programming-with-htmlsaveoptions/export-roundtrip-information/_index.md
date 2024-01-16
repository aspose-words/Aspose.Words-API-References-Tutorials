---
title: Xuất thông tin khứ hồi
linktitle: Xuất thông tin khứ hồi
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xuất thông tin khứ hồi khi lưu tài liệu dưới dạng HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/export-roundtrip-information/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để xuất thông tin khứ hồi từ tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn đưa thông tin khứ hồi vào tệp HTML đã xuất, giúp truy xuất các thay đổi được thực hiện đối với tài liệu gốc dễ dàng hơn.

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

Bây giờ chúng ta sẽ định cấu hình các tùy chọn lưu HTML để xuất thông tin khứ hồi của tài liệu. Sử dụng mã sau đây:

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };
```

 Mã này tạo ra một thể hiện của`HtmlSaveOptions`và thiết lập`ExportRoundtripInformation` tùy chọn để`true` để bao gồm thông tin khứ hồi khi xuất.

## Bước 4: Chuyển đổi và lưu tài liệu sang HTML

Cuối cùng, chúng tôi sẽ chuyển đổi tài liệu sang HTML bằng các tùy chọn lưu HTML được định cấu hình trước đó. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);
```

Mã này chuyển đổi tài liệu sang HTML bao gồm thông tin khứ hồi và lưu tệp HTML đã xuất vào thư mục được chỉ định.

### Mã nguồn ví dụ để xuất thông tin khứ hồi bằng Aspose.Words cho .NET


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	HtmlSaveOptions saveOptions = new HtmlSaveOptions { ExportRoundtripInformation = true };

	doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportRoundtripInformation.html", saveOptions);

```

 Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu trong thư mục`dataDir` Biến đổi.