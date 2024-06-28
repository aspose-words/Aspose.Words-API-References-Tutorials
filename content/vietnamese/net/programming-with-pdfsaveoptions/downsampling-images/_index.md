---
title: Giảm kích thước tài liệu PDF bằng cách lấy mẫu hình ảnh xuống
linktitle: Giảm kích thước tài liệu PDF bằng cách lấy mẫu hình ảnh xuống
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách giảm kích thước tài liệu pdf bằng cách lấy mẫu hình ảnh xuống khi chuyển đổi sang PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/downsampling-images/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để giảm kích thước tài liệu pdf bằng cách lấy mẫu hình ảnh xuống khi chuyển đổi sang PDF bằng Aspose.Words cho .NET. Điều này làm giảm kích thước của tệp PDF được tạo. Làm theo các bước dưới đây:

## Bước 1: Tải tài liệu

Bắt đầu bằng cách tải lên tài liệu bạn muốn chuyển đổi sang PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Hãy chắc chắn chỉ định đường dẫn chính xác đến tài liệu của bạn.

## Bước 2: Định cấu hình tùy chọn lưu PDF

Tạo một phiên bản của lớp PdfSaveOptions và đặt các tùy chọn thu nhỏ hình ảnh:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 Các`Resolution` thuộc tính chỉ định độ phân giải mục tiêu của hình ảnh và`ResolutionThreshold`Thuộc tính chỉ định độ phân giải tối thiểu mà dưới đó hình ảnh sẽ không bị thu nhỏ lại.

## Bước 3: Chuyển đổi tài liệu sang PDF

 Sử dụng`Save` phương pháp chuyển đổi tài liệu sang PDF chỉ định các tùy chọn lưu:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Đảm bảo chỉ định đường dẫn chính xác để lưu tệp PDF đã chuyển đổi.

### Mã nguồn ví dụ cho Lấy mẫu hình ảnh bằng cách sử dụng Aspose.Words for .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Chúng tôi có thể đặt ngưỡng tối thiểu cho việc lấy mẫu xuống.
	// Giá trị này sẽ ngăn hình ảnh thứ hai trong tài liệu đầu vào bị lấy mẫu xuống.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng giảm độ phân giải hình ảnh khi chuyển đổi sang PDF bằng Aspose.Words for .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách giảm kích thước tài liệu PDF bằng cách lấy mẫu hình ảnh khi chuyển đổi sang PDF bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được mô tả, bạn có thể dễ dàng giảm độ phân giải của hình ảnh và kích thước của tệp PDF được tạo. Đảm bảo chỉ định đường dẫn chính xác tới tài liệu của bạn và định cấu hình các tùy chọn lấy mẫu hình ảnh nếu cần. Việc giảm kích thước tệp PDF giúp chia sẻ, lưu trữ và tải tệp nhanh chóng trên các nền tảng khác nhau dễ dàng hơn. Tận hưởng lợi ích của việc giảm kích thước tài liệu PDF bằng cách lấy mẫu hình ảnh bằng Aspose.Words cho .NET.

### Các câu hỏi thường gặp

#### Câu hỏi: Việc giảm kích thước của tài liệu PDF bằng cách lấy mẫu hình ảnh là gì?
Trả lời: Giảm kích thước tài liệu PDF bằng Lấy mẫu hình ảnh là giảm kích thước của tệp PDF được tạo bằng cách giảm độ phân giải của hình ảnh khi chuyển đổi sang PDF. Điều này tối ưu hóa việc sử dụng không gian lưu trữ và giúp chia sẻ và truyền tệp PDF dễ dàng hơn.

#### Câu hỏi: Làm cách nào tôi có thể giảm kích thước tài liệu PDF bằng cách lấy mẫu hình ảnh bằng Aspose.Words cho .NET?
Đáp: Để giảm kích thước tài liệu PDF bằng cách lấy mẫu hình ảnh bằng Aspose.Words for .NET, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu bạn muốn chuyển đổi sang PDF bằng cách sử dụng`Document` lớp và chỉ định đường dẫn đến tài liệu trong thư mục tài liệu đã chỉ định.

 Định cấu hình tùy chọn lưu dưới dạng PDF bằng cách tạo một phiên bản của`PdfSaveOptions` lớp và thiết lập các tùy chọn lấy mẫu hình ảnh bằng cách sử dụng`DownsampleOptions` tài sản. Bạn có thể chỉ định độ phân giải mục tiêu của hình ảnh bằng cách sử dụng`Resolution` thuộc tính và đặt ngưỡng độ phân giải tối thiểu trên đó hình ảnh sẽ không được thu nhỏ bằng cách sử dụng`ResolutionThreshold` tài sản.

 Lưu tài liệu ở định dạng PDF bằng cách sử dụng`Save` phương pháp của`Document` lớp chỉ định đường dẫn và các tùy chọn lưu.

#### Câu hỏi: Lợi ích của việc giảm kích thước tài liệu PDF bằng lấy mẫu hình ảnh là gì?
Đáp: Lợi ích của việc giảm kích thước tài liệu PDF bằng lấy mẫu hình ảnh là:

Giảm kích thước tệp PDF: Việc lấy mẫu hình ảnh làm giảm độ phân giải của hình ảnh trong tài liệu PDF, dẫn đến kích thước tệp PDF giảm đáng kể. Điều này giúp bạn dễ dàng chia sẻ và truyền tệp, đặc biệt là qua email hoặc trực tuyến.

Tối ưu hóa không gian lưu trữ: Việc giảm kích thước tệp PDF giúp tối ưu hóa việc sử dụng không gian lưu trữ, đặc biệt khi bạn có nhiều tệp PDF chứa hình ảnh có độ phân giải cao.

Cải thiện hiệu suất: Các tệp PDF nhỏ hơn tải nhanh hơn và có thể mở và xem nhanh hơn trên các thiết bị khác nhau.