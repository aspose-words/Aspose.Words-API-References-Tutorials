---
title: Thiết lập trang khác nhau
linktitle: Thiết lập trang khác nhau
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách nối thêm tài liệu với các cài đặt thiết lập trang khác nhau bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/different-page-setup/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để nối thêm tài liệu với các cài đặt thiết lập trang khác vào tài liệu khác. Mã nguồn được cung cấp trình bày cách thiết lập các cài đặt trang khác nhau cho tài liệu nguồn và đích cũng như đảm bảo tính liên tục và đánh số phù hợp.

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

## Bước 3: Thiết lập cài đặt trang cho tài liệu nguồn

 Điều chỉnh cài đặt thiết lập trang của tài liệu nguồn để đảm bảo tính liên tục và đánh số phù hợp. Trong ví dụ này, chúng tôi đặt phần bắt đầu thành`SectionStart.Continuous` và bắt đầu lại việc đánh số trang. Chúng tôi cũng đảm bảo rằng chiều rộng, chiều cao và hướng của trang khớp với phần cuối cùng của tài liệu đích.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
```

## Bước 4: Sửa đổi định dạng đoạn văn

 Để duy trì định dạng phù hợp, hãy lặp qua tất cả các đoạn văn trong tài liệu nguồn và đặt`KeepWithNext`tài sản để`true`Điều này đảm bảo rằng các đoạn văn luôn ở cùng nhau trong quá trình nối thêm.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Bước 5: Nối tài liệu nguồn vào tài liệu đích

 Sử dụng`AppendDocument` phương pháp của tài liệu đích để nối thêm tài liệu nguồn đã sửa đổi vào tài liệu đích, giữ nguyên định dạng nguồn.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 6: Lưu tài liệu đích

 Cuối cùng, lưu tài liệu đích đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```

Điều này hoàn tất việc triển khai việc thêm tài liệu với các cài đặt thiết lập trang khác nhau bằng Aspose.Words for .NET.

### Mã nguồn mẫu cho Thiết lập trang khác nhau bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Đặt tài liệu nguồn tiếp tục ngay sau khi kết thúc tài liệu đích.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Bắt đầu lại việc đánh số trang ở đầu tài liệu nguồn.
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	srcDoc.FirstSection.PageSetup.PageStartingNumber = 1;
	// Để đảm bảo điều này không xảy ra khi tài liệu nguồn có các cài đặt thiết lập trang khác nhau, hãy đảm bảo
	// cài đặt giống hệt nhau giữa phần cuối cùng của tài liệu đích.
	// Nếu có thêm các phần liên tục tiếp theo trong tài liệu nguồn,
	//điều này sẽ cần phải được lặp lại cho những phần đó.
	srcDoc.FirstSection.PageSetup.PageWidth = dstDoc.LastSection.PageSetup.PageWidth;
	srcDoc.FirstSection.PageSetup.PageHeight = dstDoc.LastSection.PageSetup.PageHeight;
	srcDoc.FirstSection.PageSetup.Orientation = dstDoc.LastSection.PageSetup.Orientation;
	// Lặp lại qua tất cả các phần trong tài liệu nguồn.
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.DifferentPageSetup.docx");
```