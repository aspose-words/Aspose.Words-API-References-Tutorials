---
title: Định cấu hình liên kết đến nội dung
linktitle: Định cấu hình liên kết đến nội dung
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để thiết lập liên kết đến nội dung trong tài liệu bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/configuring-link-to-content/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để thiết lập liên kết đến nội dung bằng Aspose.Words cho .NET. Tính năng này cho phép bạn liên kết đến nội dung cụ thể trong tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tạo tài liệu và hàm tạo

Trong bước này, chúng ta sẽ tạo một tài liệu mới và khởi tạo hàm tạo. Sử dụng mã sau đây:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Tạo dấu trang

Bây giờ chúng ta sẽ tạo một dấu trang trong tài liệu. Sử dụng đoạn mã sau để tạo dấu trang có văn bản bên trong:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Mã này tạo một dấu trang có tên "MyBookmark" và thêm một số văn bản vào bên trong.

## Bước 4: Thiết lập liên kết nội dung

Bây giờ chúng ta sẽ định cấu hình liên kết đến nội dung bằng cách sử dụng các thuộc tính của tài liệu. Sử dụng đoạn mã sau để thêm và truy xuất liên kết đến nội dung:

```csharp
// Lấy danh sách tất cả các thuộc tính tùy chỉnh trong tài liệu.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Thêm thuộc tính giới hạn nội dung.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Mã này thêm thuộc tính liên quan đến nội dung được gọi là "Dấu trang" với dấu trang "MyBookmark". Sau đó, nó truy xuất thông tin thuộc tính liên quan đến nội dung như trạng thái liên kết, nguồn liên kết và giá trị thuộc tính.

### Mã nguồn mẫu để định cấu hình liên kết tới nội dung bằng Aspose.Words cho .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Truy xuất danh sách tất cả các thuộc tính tài liệu tùy chỉnh từ tệp.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Thêm thuộc tính liên kết đến nội dung.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Bây giờ bạn đã học cách định cấu hình liên kết đến nội dung trong tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng tạo và định cấu hình liên kết đến nội dung cụ thể trong tài liệu của riêng mình.