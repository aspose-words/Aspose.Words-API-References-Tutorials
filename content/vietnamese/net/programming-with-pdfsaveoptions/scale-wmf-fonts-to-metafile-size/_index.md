---
title: Giảm kích thước PDF bằng cách chia tỷ lệ phông chữ Wmf thành kích thước siêu tệp
linktitle: Giảm kích thước PDF bằng cách chia tỷ lệ phông chữ Wmf thành kích thước siêu tệp
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để giảm kích thước pdf bằng phông chữ wmf chia tỷ lệ thành kích thước kích thước siêu tệp khi chuyển đổi sang PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---

Bài viết này cung cấp hướng dẫn từng bước về cách giảm kích thước pdf bằng phông chữ wmf tỷ lệ thành tính năng kích thước siêu tệp bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Ở cuối hướng dẫn này, bạn sẽ có thể hiểu cách bật hoặc tắt tỷ lệ phông chữ WMF khi chuyển đổi sang PDF.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu lên

Tiếp theo, chúng ta cần tải tài liệu mà chúng ta muốn xử lý. Trong ví dụ này, chúng tôi giả sử tài liệu có tên là "WMF with text.docx" và nằm trong thư mục tài liệu được chỉ định.

```csharp
Document doc = new Document(dataDir + "WMF with text.docx");
```

## Bước 3: Định cấu hình tùy chọn hiển thị siêu tệp

 Để bật hoặc tắt tỷ lệ phông chữ WMF theo kích thước siêu tệp, chúng ta cần định cấu hình`MetafileRenderingOptions`sự vật. Trong ví dụ này, chúng tôi vô hiệu hóa việc chia tỷ lệ phông chữ bằng cách đặt`ScaleWmfFontsToMetafileSize`tài sản để`false`.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     ScaleWmfFontsToMetafileSize=false
};
```

## Bước 4: Định cấu hình tùy chọn lưu dưới dạng PDF với tùy chọn hiển thị siêu tệp

Cuối cùng, chúng ta có thể định cấu hình các tùy chọn lưu thành PDF bằng cách sử dụng các tùy chọn hiển thị siêu tệp được định cấu hình trước đó.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };
```

## Bước 5: Lưu tài liệu dưới dạng PDF với tùy chọn kết xuất Metafile

Lưu tài liệu ở định dạng PDF bằng các tùy chọn lưu đã định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

Đó là tất cả ! Bạn đã bật hoặc tắt thành công tỷ lệ phông chữ WMF thành kích thước siêu tệp khi chuyển đổi

một tài liệu PDF sử dụng Aspose.Words cho .NET.

### Mã nguồn ví dụ để chia tỷ lệ phông chữ WMF thành kích thước siêu tệp với Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with text.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		ScaleWmfFontsToMetafileSize = false
	};

	// Nếu Aspose.Words không thể hiển thị chính xác một số bản ghi siêu tệp thành đồ họa vector
	// sau đó Aspose.Words hiển thị siêu tệp này thành bitmap.
	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
	
        
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách bật hoặc tắt việc thay đổi kích thước phông chữ WMF thành kích thước siêu tệp trong tài liệu PDF bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được mô tả, bạn có thể dễ dàng kiểm soát liệu phông chữ WMF có nên được thay đổi kích thước để phù hợp với kích thước siêu tệp khi chuyển đổi sang tài liệu PDF hay không. Điều này có thể giúp bạn giảm kích thước tệp PDF được tạo và cải thiện hiệu suất hiển thị. Hãy đảm bảo chỉ định đường dẫn chính xác tới tài liệu của bạn và định cấu hình các tùy chọn hiển thị siêu tệp nếu cần.

### Các câu hỏi thường gặp

#### Câu hỏi: Việc thay đổi kích thước phông chữ WMF thành kích thước siêu tệp trong tài liệu PDF là gì?
Trả lời: Thay đổi kích thước phông chữ WMF thành kích thước siêu tệp trong tài liệu PDF là tính năng kiểm soát xem phông chữ WMF có nên được điều chỉnh tỷ lệ để phù hợp với kích thước siêu tệp khi chuyển đổi sang tài liệu PDF hay không. Khi tính năng này được bật, phông chữ WMF sẽ được chia tỷ lệ để phù hợp với kích thước của siêu tệp, điều này có thể làm giảm kích thước của tài liệu PDF được tạo.

#### Câu hỏi: Làm cách nào tôi có thể sử dụng Aspose.Words cho .NET để bật hoặc tắt việc thay đổi kích thước phông chữ WMF thành kích thước siêu tệp trong tài liệu PDF?
Trả lời: Để bật hoặc tắt việc thay đổi kích thước phông chữ WMF thành kích thước siêu tệp trong tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu bạn muốn xử lý bằng cách sử dụng`Document` class và chỉ định đường dẫn đến tài liệu Word trong thư mục tài liệu đã chỉ định.

 Định cấu hình các tùy chọn hiển thị siêu tệp bằng cách tạo một phiên bản của`MetafileRenderingOptions` lớp và thiết lập`ScaleWmfFontsToMetafileSize`tài sản để`true` để cho phép chia tỷ lệ phông chữ WMF theo kích thước siêu tệp hoặc để`false` để vô hiệu hóa tính năng này.

 Định cấu hình tùy chọn lưu dưới dạng PDF bằng cách tạo một phiên bản của`PdfSaveOptions` class và sử dụng các tùy chọn kết xuất siêu tệp được định cấu hình trước đó.

 Lưu tài liệu ở định dạng PDF bằng cách sử dụng`Save` phương pháp của`Document` lớp chỉ định đường dẫn và các tùy chọn lưu.

#### Câu hỏi: Lợi ích của việc thay đổi kích thước phông chữ WMF thành kích thước siêu tệp trong tài liệu PDF là gì?
Trả lời: Ưu điểm của việc thay đổi kích thước phông chữ WMF thành kích thước siêu tệp trong tài liệu PDF là:

Giảm kích thước tệp PDF: Thay đổi kích thước phông chữ WMF thành kích thước siêu tệp có thể giảm kích thước của tài liệu PDF được tạo bằng cách điều chỉnh kích thước phông chữ cho phù hợp với nhu cầu của siêu tệp.

Cải thiện hiệu suất: Bằng cách điều chỉnh kích thước phông chữ WMF theo kích thước của siêu tệp, việc hiển thị tài liệu PDF có thể nhanh hơn và hiệu quả hơn.