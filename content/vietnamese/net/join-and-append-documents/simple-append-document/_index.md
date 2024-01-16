---
title: Tài liệu nối thêm đơn giản
linktitle: Tài liệu nối thêm đơn giản
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối và nối các tài liệu Word với định dạng được giữ nguyên bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/simple-append-document/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Nối tài liệu đơn giản của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối các tài liệu Word mà không có tùy chọn bổ sung.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:

1. Đã cài đặt Aspose.Words cho .NET. Bạn có thể tải xuống từ trang web Aspose hoặc cài đặt nó qua NuGet.
2. Visual Studio hoặc bất kỳ môi trường phát triển C# nào khác.

## Bước 1: Khởi tạo thư mục tài liệu

 Đầu tiên, bạn cần đặt đường dẫn đến thư mục tài liệu của mình. Sửa đổi giá trị của`dataDir` có thể thay đổi đường dẫn chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu nguồn và đích

 Tiếp theo, bạn cần tải tài liệu nguồn và đích bằng Aspose.Words`Document` lớp học. Cập nhật tên tập tin trong`Document` hàm tạo theo tên tài liệu của bạn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.KeepSourceFormatting` tham số đảm bảo rằng định dạng nguồn được giữ nguyên trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 4: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất bằng tính năng Nối tài liệu đơn giản bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Mã nguồn ví dụ cho Tài liệu nối thêm đơn giản bằng Aspose.Words cho .NET

Đây là mã nguồn đầy đủ cho tính năng "Tài liệu nối thêm đơn giản" trong C# bằng cách sử dụng Aspose.Words cho .NET:

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Nối tài liệu nguồn vào tài liệu đích mà không cần thêm tùy chọn nào.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Nối tài liệu đơn giản bằng Aspose.Words cho .NET. Tài liệu cuối cùng sẽ chứa nội dung đã hợp nhất với định dạng nguồn được giữ nguyên.