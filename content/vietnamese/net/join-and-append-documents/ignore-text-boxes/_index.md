---
title: Bỏ qua hộp văn bản
linktitle: Bỏ qua hộp văn bản
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối thêm tài liệu trong khi bỏ qua định dạng hộp văn bản bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/ignore-text-boxes/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để nối thêm tài liệu trong khi vẫn giữ nguyên định dạng của hộp văn bản. Mã nguồn được cung cấp trình bày cách thiết lập các tùy chọn định dạng nhập để bao gồm các hộp văn bản trong quá trình nối thêm.

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

## Bước 3: Thiết lập tùy chọn định dạng nhập

 Tạo một thể hiện của`ImportFormatOptions` lớp và thiết lập`IgnoreTextBoxes`tài sản để`false`. Điều này đảm bảo rằng các hộp văn bản được đưa vào trong quá trình nối thêm trong khi vẫn giữ nguyên định dạng của chúng.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
```

## Bước 4: Nối nội dung hộp văn bản

 Tạo một`NodeImporter`đối tượng và sử dụng nó để nhập các nút hộp văn bản từ tài liệu nguồn sang tài liệu đích. Lặp lại từng đoạn trong tài liệu nguồn và nhập nó vào tài liệu đích.

```csharp
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Bước 5: Lưu tài liệu đích

Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```

Điều này hoàn tất việc triển khai thêm tài liệu trong khi vẫn giữ nguyên định dạng hộp văn bản bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Bỏ qua hộp văn bản bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Giữ nguyên định dạng hộp văn bản nguồn khi nhập.
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreTextBoxes = false };
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
		importFormatOptions);
	ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
	foreach (Paragraph srcPara in srcParas)
	{
		Node importedNode = importer.ImportNode(srcPara, true);
		dstDoc.FirstSection.Body.AppendChild(importedNode);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.IgnoreTextBoxes.docx");
```