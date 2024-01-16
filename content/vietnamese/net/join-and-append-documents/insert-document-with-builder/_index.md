---
title: Chèn tài liệu bằng Builder
linktitle: Chèn tài liệu bằng Builder
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn tài liệu vào cuối tài liệu khác bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/insert-document-with-builder/
---

 Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để chèn tài liệu vào tài liệu khác bằng cách sử dụng`DocumentBuilder` lớp học. Mã nguồn được cung cấp trình bày cách chèn tài liệu vào cuối tài liệu khác trong khi vẫn giữ nguyên định dạng nguồn.

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

## Bước 3: Khởi tạo DocumentBuilder

 Tạo một phiên bản mới của`DocumentBuilder` lớp và chuyển tài liệu đích làm tham số.

```csharp
DocumentBuilder builder = new DocumentBuilder(dstDoc);
```

## Bước 4: Định vị DocumentBuilder

 Di chuyển`DocumentBuilder` đến cuối tài liệu bằng cách sử dụng`MoveToDocumentEnd` phương pháp. Chèn ngắt trang để tách nội dung hiện có khỏi tài liệu được chèn.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
```

## Bước 5: Chèn tài liệu nguồn

 Sử dụng`InsertDocument` phương pháp của`DocumentBuilder` class để chèn tài liệu nguồn vào tài liệu đích. Đặt chế độ định dạng nhập thành`ImportFormatMode.KeepSourceFormatting` để giữ nguyên định dạng nguồn.

```csharp
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 6: Lưu tài liệu đã sửa đổi

 Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```

Điều này hoàn tất việc thực hiện chèn tài liệu vào tài liệu khác bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Insert Document With Builder bằng Aspose.Words for .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	DocumentBuilder builder = new DocumentBuilder(dstDoc);
	builder.MoveToDocumentEnd();
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	builder.Document.Save(dataDir + "JoinAndAppendDocuments.InsertDocumentWithBuilder.docx");
```