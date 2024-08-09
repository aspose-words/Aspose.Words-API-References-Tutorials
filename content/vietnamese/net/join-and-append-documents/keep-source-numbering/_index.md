---
title: Giữ đánh số nguồn
linktitle: Giữ đánh số nguồn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nhập tài liệu trong khi vẫn giữ nguyên định dạng bằng Aspose.Words cho .NET. Hướng dẫn từng bước với các ví dụ về mã.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/keep-source-numbering/
---
## Giới thiệu

 Khi làm việc với Aspose.Words cho .NET, việc nhập tài liệu từ nguồn này sang nguồn khác trong khi vẫn giữ nguyên định dạng có thể được xử lý một cách hiệu quả bằng cách sử dụng`NodeImporter` lớp học. Hướng dẫn này sẽ hướng dẫn bạn từng bước thực hiện quy trình.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo bạn có những điều sau:
- Visual Studio được cài đặt trên máy của bạn.
-  Đã cài đặt Aspose.Words cho .NET. Nếu không, hãy tải xuống từ[đây](https://releases.aspose.com/words/net/).
- Kiến thức cơ bản về lập trình C# và .NET.

## Nhập không gian tên

Đầu tiên, bao gồm các không gian tên cần thiết trong dự án của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Bước 1: Thiết lập dự án của bạn

Bắt đầu bằng cách tạo một dự án C# mới trong Visual Studio và cài đặt Aspose.Words thông qua Trình quản lý gói NuGet.

## Bước 2: Khởi tạo tài liệu
Tạo các phiên bản của nguồn (`srcDoc`) và đích đến (`dstDoc`) tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Định cấu hình tùy chọn nhập
Thiết lập các tùy chọn nhập để duy trì định dạng nguồn, bao gồm các đoạn được đánh số.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Bước 4: Nhập đoạn văn
Lặp lại các đoạn văn trong tài liệu nguồn và nhập chúng vào tài liệu đích.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Bước 5: Lưu tài liệu
Lưu tài liệu đã hợp nhất vào vị trí mong muốn của bạn.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Phần kết luận

 Tóm lại, việc sử dụng Aspose.Words for .NET để nhập tài liệu trong khi vẫn giữ nguyên định dạng thật đơn giản với`NodeImporter` lớp học. Phương pháp này đảm bảo rằng tài liệu của bạn duy trì hình thức và cấu trúc ban đầu một cách liền mạch.

## Câu hỏi thường gặp

### Tôi có thể nhập tài liệu với các kiểu định dạng khác nhau không?
 Vâng, cái`NodeImporter` lớp hỗ trợ nhập tài liệu với nhiều kiểu định dạng khác nhau.

### Điều gì sẽ xảy ra nếu tài liệu của tôi chứa các bảng và hình ảnh phức tạp?
Aspose.Words for .NET xử lý các cấu trúc phức tạp như bảng và hình ảnh trong quá trình nhập.

### Aspose.Words có tương thích với tất cả các phiên bản .NET không?
Aspose.Words hỗ trợ các phiên bản .NET Framework và .NET Core để tích hợp liền mạch.

### Làm cách nào để xử lý lỗi trong quá trình nhập tài liệu?
Sử dụng các khối thử bắt để xử lý các trường hợp ngoại lệ có thể xảy ra trong quá trình nhập.

### Tôi có thể tìm tài liệu chi tiết hơn về Aspose.Words cho .NET ở đâu?
 Ghé thăm[tài liệu](https://reference.aspose.com/words/net/) để có hướng dẫn toàn diện và tài liệu tham khảo API.
