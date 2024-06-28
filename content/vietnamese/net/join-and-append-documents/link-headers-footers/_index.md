---
title: Liên kết Đầu trang Chân trang
linktitle: Liên kết Đầu trang Chân trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách liên kết đầu trang và chân trang trong khi nối và nối thêm tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/link-headers-footers/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Chân trang của Tiêu đề Liên kết của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối nhiều tài liệu Word đồng thời liên kết đầu trang và chân trang của tài liệu nguồn với phần trước trong tài liệu đích.

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

## Bước 3: Đặt tài liệu được thêm vào để xuất hiện trên trang mới

 Để đảm bảo rằng nội dung từ tài liệu nguồn xuất hiện trên một trang mới trong tài liệu đích, bạn cần đặt`SectionStart` thuộc tính của phần đầu tiên trong tài liệu nguồn để`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Bước 4: Liên kết đầu trang và chân trang với phần trước

 Để liên kết đầu trang và chân trang của tài liệu nguồn với phần trước đó trong tài liệu đích, bạn có thể sử dụng`LinkToPrevious` phương pháp của`HeadersFooters` bộ sưu tập. Bằng cách vượt qua`true` làm tham số, bạn ghi đè mọi đầu trang hoặc chân trang hiện có trong tài liệu nguồn.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Bước 5: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.KeepSourceFormatting` tham số đảm bảo rằng định dạng nguồn được giữ nguyên trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 6: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất với đầu trang và chân trang được liên kết bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Mã nguồn mẫu cho Chân trang đầu trang liên kết sử dụng Aspose.Words cho .NET 

Đây là mã nguồn đầy đủ cho tính năng "Liên kết chân trang đầu trang" trong C# bằng cách sử dụng Aspose.Words cho .NET:


```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Đặt tài liệu được nối thêm xuất hiện trên một trang mới.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Liên kết đầu trang và chân trang trong tài liệu nguồn với phần trước đó.
	// Điều này sẽ ghi đè mọi đầu trang hoặc chân trang đã được tìm thấy trong tài liệu nguồn.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Chân trang của Tiêu đề Liên kết bằng Aspose.Words cho .NET. Tài liệu cuối cùng sẽ chứa nội dung đã hợp nhất với các đầu trang và chân trang từ tài liệu nguồn được liên kết với phần trước trong tài liệu đích.