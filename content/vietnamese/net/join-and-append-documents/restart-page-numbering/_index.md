---
title: Khởi động lại đánh số trang
linktitle: Khởi động lại đánh số trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách bắt đầu lại việc đánh số trang trong khi nối và nối thêm tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/restart-page-numbering/
---

Hướng dẫn này sẽ hướng dẫn bạn trong quá trình sử dụng tính năng Khởi động lại đánh số trang của Aspose.Words cho .NET. Tính năng này cho phép bạn nối và nối các tài liệu Word trong khi khởi động lại việc đánh số trang trong tài liệu nguồn.

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

## Bước 3: Đặt tài liệu nguồn để khởi động lại đánh số trang

 Để khởi động lại việc đánh số trang trong tài liệu nguồn, bạn cần đặt`SectionStart` thuộc tính của phần đầu tiên trong tài liệu nguồn để`SectionStart.NewPage` và thiết lập`RestartPageNumbering`tài sản để`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Bước 4: Nối tài liệu nguồn vào tài liệu đích

 Bây giờ, bạn có thể nối tài liệu nguồn vào tài liệu đích bằng cách sử dụng`AppendDocument` phương pháp của`Document` lớp học. Các`ImportFormatMode.KeepSourceFormatting` tham số đảm bảo rằng định dạng nguồn được giữ nguyên trong thao tác chắp thêm.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 5: Lưu tài liệu cuối cùng

 Cuối cùng, lưu tài liệu đã hợp nhất với tính năng Khởi động lại đánh số trang được bật bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Mã nguồn ví dụ để khởi động lại đánh số trang bằng Aspose.Words cho .NET

Đây là mã nguồn đầy đủ cho tính năng "Khởi động lại đánh số trang" trong C# bằng Aspose.Words cho .NET:
 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Đó là nó! Bạn đã triển khai thành công tính năng Khởi động lại đánh số trang bằng Aspose.Words cho .NET. Tài liệu cuối cùng sẽ chứa nội dung được hợp nhất với việc đánh số trang được bắt đầu lại trong tài liệu nguồn.