---
title: Nối tài liệu
linktitle: Nối tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối nội dung của tài liệu này vào tài liệu khác bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/append-document/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để nối nội dung của tài liệu này vào tài liệu khác. Mã nguồn được cung cấp trình bày cách mở tài liệu nguồn và đích, nhập và nối các phần từ tài liệu nguồn vào tài liệu đích.

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

## Bước 3: Nối các phần từ tài liệu nguồn vào tài liệu đích

 Lặp lại tất cả các phần trong tài liệu nguồn và nhập từng phần vào tài liệu đích bằng cách sử dụng`ImportNode` phương pháp. Sau đó, nối phần đã nhập vào tài liệu đích.

```csharp
foreach (Section srcSection in srcDoc)
{
    Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
    dstDoc.AppendChild(dstSection);
}
```

## Bước 4: Lưu tài liệu đích

 Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```

Điều này hoàn tất việc triển khai thêm tài liệu bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Nối tài liệu bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Lặp lại tất cả các phần trong tài liệu nguồn.
	//Các nút phần là con trực tiếp của nút Tài liệu nên chúng ta chỉ có thể liệt kê Tài liệu.
	foreach (Section srcSection in srcDoc)
	{
		// Bởi vì chúng ta đang sao chép một phần từ tài liệu này sang tài liệu khác,
		// cần phải nhập nút Phần vào tài liệu đích.
		// Điều này điều chỉnh mọi tham chiếu cụ thể của tài liệu về kiểu, danh sách, v.v.
		//
		// Việc nhập một nút sẽ tạo một bản sao của nút gốc, nhưng bản sao
		// ss đã sẵn sàng để được chèn vào tài liệu đích.
		Node dstSection = dstDoc.ImportNode(srcSection, true, ImportFormatMode.KeepSourceFormatting);
		// Bây giờ nút phần mới có thể được thêm vào tài liệu đích.
		dstDoc.AppendChild(dstSection);
	}
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendDocument.docx");
```