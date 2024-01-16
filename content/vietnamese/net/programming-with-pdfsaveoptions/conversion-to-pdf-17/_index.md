---
title: Chuyển đổi tài liệu Word sang PDF 1.7
linktitle: Chuyển đổi tài liệu Word sang PDF 1.7
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi tài liệu word sang PDF 1.7 bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước cách chuyển đổi tài liệu word sang PDF 1.7 bằng Aspose.Words cho .NET. Chuyển đổi sang PDF 1.7 cho phép bạn tạo các tệp PDF phù hợp với tiêu chuẩn PDF 1.7. Làm theo các bước dưới đây:

## Bước 1: Tải tài liệu

Bắt đầu bằng cách tải lên tài liệu bạn muốn chuyển đổi sang PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Hãy chắc chắn chỉ định đường dẫn chính xác đến tài liệu của bạn.

## Bước 2: Đặt tùy chọn chuyển đổi PDF

Tạo một phiên bản của lớp PdfSaveOptions và chỉ định phiên bản của tiêu chuẩn PDF bạn muốn sử dụng:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Tùy chọn này đảm bảo rằng tệp PDF được tạo tuân thủ tiêu chuẩn PDF 1.7.

## Bước 3: Chuyển đổi tài liệu sang PDF

 Sử dụng`Save` phương pháp chuyển đổi tài liệu sang PDF chỉ định các tùy chọn chuyển đổi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Đảm bảo chỉ định đường dẫn chính xác để lưu tệp PDF đã chuyển đổi.

### Mã nguồn ví dụ cho Chuyển đổi sang Pdf 17 bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để chuyển đổi sang PDF 1.7 bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng chuyển đổi sang PDF 1.7 bằng Aspose.Words cho .NET.


## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách chuyển đổi tài liệu Word sang PDF 1.7 bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được mô tả, bạn có thể dễ dàng tạo các tệp PDF tuân thủ tiêu chuẩn PDF 1.7. Đảm bảo chỉ định đường dẫn chính xác tới tài liệu Word của bạn và định cấu hình các tùy chọn chuyển đổi sang PDF nếu cần. Chuyển đổi sang PDF 1.7 đảm bảo khả năng tương thích và dễ đọc tối ưu trên các nền tảng khác nhau.

### Các câu hỏi thường gặp

#### Hỏi: Chuyển đổi Word sang PDF 1.7 là gì?
Trả lời: Chuyển đổi tài liệu Word sang PDF 1.7 là tạo ra các tệp PDF phù hợp với tiêu chuẩn PDF 1.7. Tiêu chuẩn này quy định các tính năng và yêu cầu đối với tệp PDF, cho phép khả năng tương thích và dễ đọc tối ưu trên các nền tảng khác nhau.

#### Hỏi: Làm cách nào tôi có thể chuyển đổi tài liệu Word sang PDF 1.7 bằng Aspose.Words cho .NET?
Trả lời: Để chuyển đổi tài liệu Word sang PDF 1.7 bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu Word bạn muốn chuyển đổi sang PDF bằng cách sử dụng`Document` class và chỉ định đường dẫn đến tài liệu Word trong thư mục tài liệu đã chỉ định.

 Định cấu hình chuyển đổi dưới dạng tùy chọn PDF bằng cách tạo một phiên bản của`PdfSaveOptions`lớp và chỉ định phiên bản của tiêu chuẩn PDF bạn muốn sử dụng bằng cách sử dụng`Compliance` tài sản có giá trị`PdfCompliance. Pdf17` để tạo tệp PDF tuân thủ tiêu chuẩn PDF 1.7.

 Lưu tài liệu ở định dạng PDF bằng cách sử dụng`Save` phương pháp của`Document` lớp chỉ định đường dẫn và các tùy chọn lưu.

#### Hỏi: Lợi ích của việc chuyển đổi sang PDF 1.7 bằng Aspose.Words cho .NET là gì?
Trả lời: Ưu điểm của việc chuyển đổi sang PDF 1.7 bằng Aspose.Words cho .NET là:

Tuân thủ PDF 1.7: Chuyển đổi sang PDF 1.7 đảm bảo rằng tệp PDF được tạo tuân thủ PDF 1.7, đảm bảo khả năng tương thích và dễ đọc trên các nền tảng khác nhau.

Bảo toàn định dạng tài liệu: Aspose.Words for .NET đảm bảo chuyển đổi tài liệu Word chính xác bằng cách giữ nguyên định dạng, hình ảnh và kiểu, dẫn đến tệp PDF giống như bản gốc.