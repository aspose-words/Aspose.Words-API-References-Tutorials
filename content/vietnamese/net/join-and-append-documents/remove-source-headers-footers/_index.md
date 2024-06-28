---
title: Xóa chân trang đầu trang nguồn
linktitle: Xóa chân trang đầu trang nguồn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xóa đầu trang và chân trang trong khi nối và nối thêm tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/remove-source-headers-footers/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Xóa chân trang đầu trang nguồn của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối các tài liệu Word trong khi xóa đầu trang và chân trang khỏi tài liệu nguồn.

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

## Bước 3: Xóa đầu trang và chân trang khỏi phần tài liệu nguồn

 Để xóa đầu trang và chân trang khỏi mỗi phần trong tài liệu nguồn, bạn có thể lặp qua các phần bằng cách sử dụng một`foreach` vòng lặp và gọi`ClearHeadersFooters` phương pháp.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Bước 4: Tắt cài đặt "LinkToPrevious" cho HeadersFooters

Ngay cả sau khi xóa đầu trang và chân trang khỏi tài liệu nguồn, vẫn có khả năng cài đặt "LinkToPrevious" cho`HeadersFooters` vẫn có thể được thiết lập. Để tránh hành vi này, bạn cần đặt nó một cách rõ ràng thành`false` cho phần đầu tiên`HeadersFooters` tài sản.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Bước 5: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.KeepSourceFormatting` tham số đảm bảo rằng định dạng nguồn được giữ nguyên trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 6: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất với tính năng Xóa chân trang đầu trang nguồn được bật bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

### Mã nguồn ví dụ cho Xóa chân trang đầu trang nguồn bằng Aspose.Words cho .NET 

Đây là mã nguồn đầy đủ cho tính năng "Xóa chân trang đầu trang nguồn" trong C# bằng cách sử dụng Aspose.Words cho .NET:


```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Xóa đầu trang và chân trang khỏi mỗi phần trong tài liệu nguồn.
	foreach (Section section in srcDoc.Sections)
	{
		section.ClearHeadersFooters();
	}
	// Ngay cả sau khi đầu trang và chân trang bị xóa khỏi tài liệu nguồn, cài đặt "LinkToPrevious"
	// cho HeadersFooters vẫn có thể được đặt. Điều này sẽ khiến đầu trang và chân trang tiếp tục từ đích
	// tài liệu. Điều này nên được đặt thành false để tránh hành vi này.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```
Đó là nó! Bạn đã triển khai thành công tính năng Xóa chân trang đầu trang nguồn bằng Aspose.Words cho .NET. Tài liệu cuối cùng sẽ chứa nội dung được hợp nhất với các đầu trang và chân trang đã bị xóa khỏi tài liệu nguồn.