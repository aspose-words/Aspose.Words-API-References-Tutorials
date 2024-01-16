---
title: Tham gia liên tục
linktitle: Tham gia liên tục
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối hai tài liệu liên tục trong khi vẫn giữ nguyên định dạng bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/join-continuous/
---

Hướng dẫn này giải thích cách nối hai tài liệu liên tục bằng Aspose.Words cho .NET. Mã nguồn được cung cấp trình bày cách nối thêm tài liệu vào cuối tài liệu khác trong khi vẫn duy trì định dạng ban đầu.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

-  Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải nó xuống từ[Aspose.Releases]https://releases.aspose.com/words/net/ hoặc sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi chứa tài liệu nguồn và đích.

## Bước 2: Mở tài liệu nguồn và đích

 Mở tài liệu nguồn và đích bằng cách sử dụng`Document` hàm tạo lớp. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Thiết lập phần bắt đầu liên tục

 Để làm cho tài liệu nguồn xuất hiện ngay sau nội dung của tài liệu đích, hãy đặt giá trị`SectionStart` thuộc tính của phần đầu tiên trong tài liệu nguồn để`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Bước 4: Nối tài liệu nguồn

 Nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Đặt chế độ định dạng nhập thành`ImportFormatMode.KeepSourceFormatting` để giữ nguyên các kiểu gốc từ tài liệu nguồn.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 5: Lưu tài liệu đã sửa đổi

 Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

Điều này hoàn tất việc triển khai nối hai tài liệu liên tục bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Tham gia liên tục bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Làm cho tài liệu xuất hiện ngay sau nội dung tài liệu đích.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Nối tài liệu nguồn bằng cách sử dụng các kiểu gốc được tìm thấy trong tài liệu nguồn.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```