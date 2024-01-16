---
title: Nối tài liệu vào chỗ trống
linktitle: Nối tài liệu vào chỗ trống
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối tài liệu vào tài liệu đích trống trong Aspose.Words dành cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/append-document-to-blank/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để nối nội dung của một tài liệu vào tài liệu đích trống. Mã nguồn được cung cấp trình bày cách tạo một tài liệu mới, xóa nội dung của nó và sau đó nối thêm tài liệu nguồn vào đó.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

-  Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải nó xuống từ[Aspose.Releases]https://releases.aspose.com/words/net/ hoặc sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi chứa tài liệu nguồn và đích.

## Bước 2: Tạo tài liệu đích mới

 Tạo một cái mới`Document` đối tượng cho tài liệu đích.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document();
```

## Bước 3: Xóa nội dung hiện có khỏi tài liệu đích

 Để đảm bảo tài liệu đích sạch sẽ, hãy xóa tất cả nội dung hiện có khỏi tài liệu bằng cách sử dụng`RemoveAllChildren` phương pháp.

```csharp
dstDoc.RemoveAllChildren();
```

## Bước 4: Nối tài liệu nguồn vào tài liệu đích

 Nối nội dung của tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp với`ImportFormatMode.KeepSourceFormatting` lựa chọn.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 5: Lưu tài liệu đích

 Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");
```

Việc này hoàn tất việc triển khai việc thêm tài liệu vào tài liệu đích trống bằng cách sử dụng Aspose.Words for .NET.

### Mã nguồn ví dụ cho Nối tài liệu vào trống bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document();
	// Tài liệu đích không trống, thường khiến một trang trống xuất hiện trước tài liệu được nối thêm.
	// Điều này là do tài liệu cơ sở có một phần trống và tài liệu mới được bắt đầu ở trang tiếp theo.
	// Xóa tất cả nội dung khỏi tài liệu đích trước khi thêm vào.
	dstDoc.RemoveAllChildren();
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocumentToBlank.docx");

```