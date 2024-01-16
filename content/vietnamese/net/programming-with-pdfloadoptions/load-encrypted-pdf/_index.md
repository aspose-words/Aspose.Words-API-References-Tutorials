---
title: Tải PDF được mã hóa
linktitle: Tải PDF được mã hóa
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để tải tệp PDF được mã hóa bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

Khi Xử lý văn bản bằng tài liệu PDF trong ứng dụng .NET của bạn, có thể cần phải tải các tệp PDF được bảo vệ bằng mật khẩu. Aspose.Words for .NET là một thư viện mạnh mẽ cung cấp chức năng tải tài liệu PDF được mã hóa. Trong bài viết này, chúng tôi sẽ hướng dẫn bạn từng bước để hiểu và sử dụng tính năng này.

## Hiểu tính năng tải PDF được mã hóa

Tính năng Tải PDF được mã hóa của Aspose.Words cho .NET cho phép bạn tải các tệp PDF được bảo vệ bằng mật khẩu. Bạn có thể chỉ định mật khẩu khi tải tài liệu để có thể truy cập nội dung của nó và thao tác khi cần.

## Bước 1: Tải tài liệu PDF được mã hóa

Bước đầu tiên là tải tài liệu PDF được mã hóa vào ứng dụng của bạn. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Đảm bảo chỉ định đường dẫn chính xác tới tệp PDF được mã hóa trong`dataDir` Biến đổi.

## Bước 2: Mã hóa tài liệu PDF

 Nếu bạn cũng muốn mã hóa tài liệu PDF của mình, bạn có thể làm như vậy bằng cách sử dụng`PdfSaveOptions` lớp và chỉ định chi tiết mã hóa:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Thao tác này sẽ tạo phiên bản mã hóa của tài liệu PDF trong thư mục được chỉ định.

## Bước 3: Lưu tài liệu PDF được mã hóa

Sau khi tải lên và tùy chọn mã hóa tài liệu PDF, bạn có thể lưu nó ở định dạng khác hoặc xử lý thêm theo nhu cầu cụ thể của mình.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Bước 5: Tải tài liệu PDF được mã hóa bằng mật khẩu

Bảo trì

Tuy nhiên, nếu bạn muốn tải tài liệu PDF được mã hóa bằng mật khẩu, bạn phải sử dụng`PdfLoadOptions` lớp và chỉ định mật khẩu khi tải tài liệu:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Đảm bảo cung cấp đúng mật khẩu trong`Password` Biến đổi.

### Mã nguồn ví dụ để tải tệp PDF được mã hóa bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Phần kết luận

Trong bài viết này, chúng tôi đã khám phá cách sử dụng tính năng Tải PDF được mã hóa của Aspose.Words cho .NET. Bạn đã học cách tải lên tệp PDF được mã hóa, cách mã hóa tài liệu PDF, cách tải lên tệp PDF được mã hóa bằng mật khẩu và cách tạo đầu ra ở định dạng Markdown. Tính năng này cực kỳ hữu ích khi Xử lý văn bản với tài liệu PDF bảo mật.


