---
title: Bỏ qua đầu trang chân trang
linktitle: Bỏ qua đầu trang chân trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối thêm tài liệu trong khi bỏ qua nội dung đầu trang và chân trang bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/ignore-header-footer/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để nối thêm tài liệu trong khi bỏ qua nội dung đầu trang và chân trang. Mã nguồn được cung cấp trình bày cách thiết lập các tùy chọn định dạng nhập để loại trừ đầu trang và chân trang trong quá trình nối thêm.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

-  Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải nó xuống từ[Aspose.Releases]https://releases.aspose.com/words/net/ hoặc sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi chứa tài liệu nguồn và đích.

## Bước 2: Mở tài liệu nguồn và đích

 Mở tài liệu nguồn và đích bằng cách sử dụng`Document` hàm tạo lớp. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Thiết lập tùy chọn định dạng nhập

 Tạo một thể hiện của`ImportFormatOptions` lớp và thiết lập`IgnoreHeaderFooter`tài sản để`false`. Điều này đảm bảo rằng nội dung đầu trang và chân trang được đưa vào trong quá trình nối thêm.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Bước 4: Nối tài liệu nguồn vào tài liệu đích

 Sử dụng`AppendDocument` phương pháp của tài liệu đích để nối thêm tài liệu nguồn. Vượt qua`ImportFormatMode.KeepSourceFormatting`làm tham số thứ hai và các tùy chọn định dạng nhập làm tham số thứ ba.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Bước 5: Lưu tài liệu đích

Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

Điều này hoàn tất việc triển khai thêm tài liệu trong khi bỏ qua nội dung đầu trang và chân trang bằng Aspose.Words for .NET.

### Mã nguồn ví dụ cho Bỏ qua chân trang tiêu đề bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```