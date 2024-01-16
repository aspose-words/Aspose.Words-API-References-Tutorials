---
title: Giữ định dạng nguồn
linktitle: Giữ định dạng nguồn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối tài liệu nguồn vào tài liệu đích trong khi vẫn giữ nguyên định dạng ban đầu bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/keep-source-formatting/
---

Hướng dẫn này trình bày cách nối tài liệu nguồn vào tài liệu đích trong khi vẫn giữ nguyên định dạng ban đầu của tài liệu nguồn bằng Aspose.Words cho .NET.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

-  Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải nó xuống từ[Aspose.Releases]https://releases.aspose.com/words/net/ hoặc sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu nguồn và đích sẽ được lưu.

## Bước 2: Tạo tài liệu đích và nguồn

 Tạo các trường hợp của`Document` cho các tài liệu đích và nguồn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text.");

Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text.");
```

## Bước 3: Nối tài liệu nguồn vào tài liệu đích

 Sử dụng`AppendDocument` phương pháp của tài liệu đích để nối thêm tài liệu nguồn. Vượt qua`ImportFormatMode.KeepSourceFormatting` làm chế độ định dạng nhập để giữ lại định dạng ban đầu của tài liệu nguồn.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 4: Lưu tài liệu đã sửa đổi

 Lưu tài liệu đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```

Điều này hoàn tất việc triển khai việc thêm tài liệu nguồn vào tài liệu đích trong khi vẫn giữ định dạng ban đầu bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho Giữ định dạng nguồn bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document dstDoc = new Document();
	dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");
	Document srcDoc = new Document();
	srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");
	// Nối tài liệu nguồn vào tài liệu đích.
	// Chuyển chế độ định dạng để giữ lại định dạng ban đầu của tài liệu nguồn khi nhập nó.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceFormatting.docx");
```