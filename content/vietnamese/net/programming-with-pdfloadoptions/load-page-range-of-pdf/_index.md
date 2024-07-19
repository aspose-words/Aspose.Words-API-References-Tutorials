---
title: Tải phạm vi trang của PDF
linktitle: Tải phạm vi trang của PDF
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để tải một phạm vi trang PDF cụ thể bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách tải một phạm vi trang cụ thể từ tài liệu PDF bằng Aspose.Words cho .NET. Làm theo các bước dưới đây:

## Bước 1: Tải một loạt trang PDF

Sử dụng mã sau để tải một phạm vi trang cụ thể từ tài liệu PDF:

```csharp
//Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 Trong ví dụ này, chúng tôi đang tải trang đầu tiên của tài liệu PDF. Bạn có thể thay đổi các giá trị của`PageIndex`Và`PageCount` đến phạm vi trang mong muốn.

## Bước 2: Lưu tài liệu

 Cuối cùng, bạn có thể lưu tài liệu chứa phạm vi trang cụ thể bằng cách sử dụng`Save` phương pháp:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Đảm bảo chỉ định đường dẫn chính xác để lưu tài liệu đã chỉnh sửa.

Đó là tất cả ! Bây giờ bạn đã tải một phạm vi trang cụ thể từ tài liệu PDF bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ để tải phạm vi trang của Pdf bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Hãy nhớ chỉ định đường dẫn chính xác đến thư mục tài liệu PDF của bạn.



