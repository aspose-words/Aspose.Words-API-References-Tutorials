---
title: Đặt thư mục hình ảnh
linktitle: Đặt thư mục hình ảnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt thư mục hình ảnh khi xuất sang Markdown bằng Aspose.Words cho .NET. Tùy chỉnh vị trí của hình ảnh để tổ chức và tích hợp tốt hơn.
type: docs
weight: 10
url: /vi/net/programming-with-markdownsaveoptions/set-images-folder/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# sau giúp đặt thư mục hình ảnh cho các tùy chọn xuất Markdown bằng thư viện Aspose.Words cho .NET. Đảm bảo bạn đã đưa thư viện Aspose.Words vào dự án của mình trước khi sử dụng mã này.

## Bước 1: Đặt đường dẫn thư mục tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Đảm bảo chỉ định đường dẫn chính xác tới thư mục tài liệu của bạn nơi chứa tài liệu chứa hình ảnh.

## Bước 2: Tải tài liệu chứa hình ảnh

```csharp
Document doc = new Document(dataDir + "Image bullet points.docx");
```

Chúng tôi tải tài liệu được chỉ định có chứa hình ảnh mà chúng tôi muốn xuất bằng tùy chọn Markdown.

## Bước 3: Đặt thư mục hình ảnh cho tùy chọn xuất Markdown

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };
```

 Chúng tôi tạo một thể hiện của`MarkdownSaveOptions` và đặt đường dẫn đến thư mục hình ảnh bằng cách sử dụng`ImagesFolder` tài sản. Đảm bảo chỉ định đúng đường dẫn đến thư mục bạn muốn lưu hình ảnh đã xuất.

## Bước 4: Lưu tài liệu với tùy chọn xuất Markdown

```csharp
using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Chúng tôi lưu tài liệu vào luồng bộ nhớ bằng cách sử dụng các tùy chọn xuất Markdown được chỉ định. Sau đó, bạn có thể sử dụng luồng để thực hiện các thao tác khác, chẳng hạn như lưu nội dung Markdown vào một tệp.

### Mã nguồn mẫu để đặt thư mục hình ảnh cho MarkdownSaveOptions với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Image bullet points.docx");

MarkdownSaveOptions saveOptions = new MarkdownSaveOptions { ImagesFolder = dataDir + "Images" };

using (MemoryStream stream = new MemoryStream())
     doc. Save(stream, saveOptions);
```

Mã nguồn này trình bày cách tải tài liệu có chứa hình ảnh, sau đó đặt thư mục hình ảnh cho các tùy chọn xuất Markdown. Bằng cách sử dụng các tùy chọn được chỉ định, tài liệu sẽ được lưu vào luồng bộ nhớ. Điều này cho phép bạn tùy chỉnh vị trí của thư mục hình ảnh khi xuất nội dung Markdown.