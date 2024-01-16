---
title: Nén hình ảnh trong tài liệu PDF
linktitle: Nén hình ảnh trong tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để nén hình ảnh trong Tài liệu PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/image-compression/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng tính năng Nén hình ảnh trong Tài liệu PDF với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách nén hình ảnh trong tài liệu và tạo tệp PDF với khả năng nén hình ảnh phù hợp.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu lên

Tiếp theo, chúng ta cần tải tài liệu mà chúng ta muốn xử lý. Trong ví dụ này, chúng tôi giả sử tài liệu có tên là "Rendering.docx" và nằm trong thư mục tài liệu được chỉ định.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu dưới dạng PDF với tính năng nén ảnh

 Để nén hình ảnh khi chuyển đổi sang PDF, chúng ta cần cấu hình`PdfSaveOptions` sự vật. Chúng tôi có thể đặt loại nén hình ảnh, chất lượng JPEG và các tùy chọn tuân thủ PDF khác nếu được yêu cầu.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Bước 4: Lưu tài liệu dưới dạng PDF bằng cách nén hình ảnh

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng PDF bằng cách sử dụng các tùy chọn lưu đã định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Bước 5: Định cấu hình các tùy chọn lưu vào PDF/A-2u bằng tính năng nén ảnh

Nếu bạn muốn tạo tệp PDF tương thích PDF/A-2u bằng tính năng nén hình ảnh, bạn có thể định cấu hình các tùy chọn lưu bổ sung.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Sử dụng nén JPEG với chất lượng 50% để giảm kích thước tệp.
};
```

## Bước 6: Lưu tài liệu dưới dạng PDF/A-2u với tính năng nén hình ảnh

Lưu tài liệu ở định dạng PDF/A-2u bằng cách sử dụng các tùy chọn lưu bổ sung được định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Đó là tất cả ! Bạn đã nén thành công hình ảnh trong tài liệu và tạo tệp PDF với khả năng nén hình ảnh phù hợp bằng Aspose.Words cho .NET.

### Mã nguồn mẫu để nén hình ảnh bằng Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Sử dụng nén JPEG ở chất lượng 50% để giảm kích thước tệp.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách nén hình ảnh trong tài liệu PDF bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được mô tả, bạn có thể dễ dàng giảm kích thước hình ảnh trong tài liệu PDF của mình và tạo tệp PDF với khả năng nén hình ảnh phù hợp. Sử dụng các tính năng nén hình ảnh của Aspose.Words cho .NET để tối ưu hóa kích thước tài liệu PDF của bạn trong khi vẫn giữ được chất lượng hình ảnh.

### Các câu hỏi thường gặp

#### Hỏi: Nén hình ảnh trong tài liệu PDF là gì?
Trả lời: Nén hình ảnh trong tài liệu PDF là để giảm kích thước hình ảnh có trong tài liệu PDF nhằm giảm kích thước tổng thể của tệp PDF. Điều này giúp giảm dung lượng lưu trữ cần thiết và cải thiện hiệu suất khi tải và xem tệp PDF.

#### Câu hỏi: Làm cách nào tôi có thể nén hình ảnh trong tài liệu PDF bằng Aspose.Words cho .NET?
Trả lời: Để nén hình ảnh trong tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Tạo một thể hiện của`Document` lớp chỉ định đường dẫn đến tài liệu Word.

 Tạo một thể hiện của`PdfSaveOptions` lớp và thiết lập`ImageCompression`tài sản để`PdfImageCompression.Jpeg` để sử dụng nén JPEG.

Bạn cũng có thể đặt các tùy chọn nén hình ảnh khác, chẳng hạn như chất lượng JPEG, tùy theo nhu cầu của bạn.

 Sử dụng`Save` phương pháp của`Document`lớp để lưu tài liệu ở định dạng PDF bằng cách chỉ định các tùy chọn lưu.

#### Câu hỏi: Sự khác biệt giữa nén hình ảnh tiêu chuẩn và nén hình ảnh PDF/A-2u là gì?
Đáp: Nén hình ảnh tiêu chuẩn giúp giảm kích thước hình ảnh trong tài liệu PDF trong khi vẫn giữ nguyên các trường biểu mẫu. Điều này làm giảm kích thước tổng thể của tệp PDF mà không ảnh hưởng đến chức năng của trường biểu mẫu.

Nén hình ảnh bằng PDF/A-2u là một tùy chọn bổ sung cho phép bạn tạo tệp PDF phù hợp với tiêu chuẩn PDF/A-2u trong khi áp dụng nén hình ảnh. PDF/A-2u là tiêu chuẩn ISO để lưu trữ tài liệu PDF và đảm bảo việc bảo quản tài liệu lâu dài.
