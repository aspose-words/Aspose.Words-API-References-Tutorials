---
title: Nối với các tùy chọn định dạng nhập
linktitle: Nối với các tùy chọn định dạng nhập
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối thêm tài liệu với các tùy chọn định dạng nhập bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/append-with-import-format-options/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để nối nội dung của tài liệu này vào tài liệu khác với các tùy chọn định dạng nhập. Mã nguồn được cung cấp trình bày cách mở tài liệu nguồn và đích, chỉ định các tùy chọn định dạng nhập và nối tài liệu nguồn vào tài liệu đích.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

-  Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải nó xuống từ[Aspose.Releases]https://releases.aspose.com/words/net/ hoặc sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi chứa tài liệu nguồn và đích.

## Bước 2: Mở tài liệu nguồn và đích

 Mở tài liệu nguồn và đích bằng cách sử dụng`Document` hàm tạo lớp. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Bước 3: Chỉ định tùy chọn định dạng nhập

 Tạo một thể hiện của`ImportFormatOptions` class để chỉ định các tùy chọn định dạng nhập. Trong ví dụ này, chúng tôi sử dụng`KeepSourceNumbering` thuộc tính để đảm bảo rằng việc đánh số từ tài liệu nguồn được sử dụng nếu có xung đột với tài liệu đích.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Bước 4: Nối tài liệu nguồn vào tài liệu đích

 Sử dụng`AppendDocument` phương pháp của tài liệu đích để nối thêm tài liệu nguồn. Vượt qua`ImportFormatMode.UseDestinationStyles` làm tham số thứ hai để sử dụng kiểu và định dạng của tài liệu đích.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Bước 5: Lưu tài liệu đích

 Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

Điều này hoàn tất việc triển khai thêm tài liệu với các tùy chọn định dạng nhập bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Nối với các tùy chọn định dạng nhập bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Chỉ định rằng nếu việc đánh số xung đột trong tài liệu nguồn và đích,
	//sau đó đánh số từ tài liệu nguồn sẽ được sử dụng.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```