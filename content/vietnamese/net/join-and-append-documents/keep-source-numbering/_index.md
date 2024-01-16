---
title: Giữ đánh số nguồn
linktitle: Giữ đánh số nguồn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối thêm tài liệu trong khi vẫn giữ nguyên định dạng đánh số nguồn trong Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/keep-source-numbering/
---

Hướng dẫn này giải thích cách nối tài liệu nguồn vào tài liệu đích trong khi vẫn giữ nguyên định dạng đánh số ban đầu của các đoạn được đánh số bằng Aspose.Words cho .NET.

## Bước 1: Thiết lập dự án

Đảm bảo bạn có các điều kiện tiên quyết sau:

-  Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải nó xuống từ[Aspose.Releases]https://releases.aspose.com/words/net/ hoặc sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu nguồn và đích sẽ được lưu.

## Bước 2: Tạo tài liệu đích và nguồn

 Tạo các trường hợp của`Document` cho các tài liệu đích và nguồn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Giữ nguyên đánh số nguồn khi nhập

 Để duy trì định dạng đánh số của các đoạn văn được đánh số từ tài liệu nguồn, hãy tạo một phiên bản của`ImportFormatOptions` và thiết lập`KeepSourceNumbering` ĐẾN`true` . Sử dụng một`NodeImporter` để nhập các nút từ tài liệu nguồn vào tài liệu đích, chỉ định`ImportFormatMode.KeepSourceFormatting` và`importFormatOptions`.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Bước 4: Nhập và nối đoạn văn

Lặp lại các đoạn trong tài liệu nguồn và nhập từng đoạn vào tài liệu đích bằng cách sử dụng`importer`. Nối các nút đã nhập vào phần nội dung của tài liệu đích.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Bước 5: Lưu tài liệu đã sửa đổi

 Lưu tài liệu đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

Điều này hoàn tất việc triển khai việc thêm tài liệu nguồn vào tài liệu đích trong khi vẫn giữ định dạng đánh số ban đầu bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho Giữ đánh số nguồn bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Giữ định dạng danh sách nguồn khi nhập các đoạn văn được đánh số.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, false);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```