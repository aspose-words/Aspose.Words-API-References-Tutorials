---
title: Liệt kê các thuộc tính
linktitle: Liệt kê các thuộc tính
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước cách liệt kê các thuộc tính tài liệu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-document-properties/enumerate-properties/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn mã nguồn C# để liệt kê các thuộc tính tài liệu bằng Aspose.Words cho .NET. Tính năng này cho phép bạn truy cập các thuộc tính tùy chỉnh và tích hợp sẵn của tài liệu.

## Bước 1: Thiết lập dự án

Để bắt đầu, hãy tạo một dự án C# mới trong IDE yêu thích của bạn. Đảm bảo thư viện Aspose.Words for .NET được tham chiếu trong dự án của bạn.

## Bước 2: Tải tài liệu

Trong bước này, chúng tôi sẽ tải tài liệu Word có thuộc tính mà chúng tôi muốn liệt kê. Sử dụng đoạn mã sau để tải tài liệu:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

 Thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục chứa tài liệu của bạn.

## Bước 3: Liệt kê các thuộc tính

Bây giờ hãy liệt kê các thuộc tính tài liệu, cả thuộc tính tích hợp và tùy chỉnh. Sử dụng mã sau đây:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

Mã này hiển thị tên tài liệu, sau đó liệt kê các thuộc tính tùy chỉnh và tích hợp hiển thị tên và giá trị của chúng.

### Mã nguồn ví dụ cho Liệt kê các thuộc tính bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

 Đảm bảo chỉ định đường dẫn tài liệu chính xác trong`dataDir` Biến đổi.

Bây giờ bạn đã học cách liệt kê các thuộc tính tài liệu bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước được cung cấp trong hướng dẫn này, bạn có thể dễ dàng truy cập và xem các thuộc tính của tài liệu của riêng mình.

