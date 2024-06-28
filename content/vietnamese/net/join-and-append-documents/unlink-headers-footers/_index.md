---
title: Bỏ liên kết đầu trang chân trang
linktitle: Bỏ liên kết đầu trang chân trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối và nối các tài liệu Word trong khi hủy liên kết đầu trang và chân trang bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/unlink-headers-footers/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Unlink Headers Footers của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối các tài liệu Word trong khi hủy liên kết đầu trang và chân trang khỏi tài liệu nguồn.

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

Tiếp theo, bạn cần tải tài liệu nguồn và đích bằng Aspose.Words.`Document` lớp học. Cập nhật tên tập tin trong`Document` hàm tạo theo tên tài liệu của bạn.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Hủy liên kết đầu trang và chân trang trong tài liệu nguồn

 Để hủy liên kết đầu trang và chân trang trong tài liệu nguồn khỏi việc tiếp tục đầu trang và chân trang của tài liệu đích, bạn cần đặt`LinkToPrevious` tài sản của`HeadersFooters` tập hợp trong phần đầu tiên của tài liệu nguồn để`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Bước 4: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.KeepSourceFormatting` tham số đảm bảo rằng định dạng nguồn được giữ nguyên trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 5: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất với tính năng Unlink Headers Footers được bật bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Mã nguồn mẫu cho Unlink Headers Footers sử dụng Aspose.Words for .NET

Đây là mã nguồn đầy đủ cho tính năng "Hủy liên kết chân trang đầu trang" trong C# bằng cách sử dụng Aspose.Words cho .NET:

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Hủy liên kết đầu trang và chân trang trong tài liệu nguồn để dừng việc này
	// tiếp tục đầu trang và chân trang của tài liệu đích.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Unlink Headers Footers bằng Aspose.Words for .NET. Tài liệu cuối cùng sẽ chứa nội dung đã hợp nhất với các đầu trang và chân trang từ tài liệu nguồn được hủy liên kết khỏi tài liệu đích.