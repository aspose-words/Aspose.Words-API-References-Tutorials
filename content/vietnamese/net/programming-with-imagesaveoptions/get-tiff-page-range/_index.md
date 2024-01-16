---
title: Nhận phạm vi trang Tiff
linktitle: Nhận phạm vi trang Tiff
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách trích xuất một loạt trang TIFF bằng Aspose.Words cho .NET. Hướng dẫn đầy đủ về các tệp TIFF tùy chỉnh.
type: docs
weight: 10
url: /vi/net/programming-with-imagesaveoptions/get-tiff-page-range/
---

Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp để có được nhiều trang TIFF với Aspose.Words cho .NET. Tính năng này cho phép bạn trích xuất một phạm vi trang cụ thể từ tài liệu và lưu chúng dưới dạng tệp TIFF.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập môi trường phát triển của mình với Aspose.Words for .NET. Đảm bảo bạn đã thêm các tham chiếu cần thiết và nhập các không gian tên thích hợp.

## Bước 2: Tải tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Ở bước này, chúng ta tải tài liệu bằng cách sử dụng`Document` phương thức và chuyển đường dẫn đến tệp DOCX để tải.

## Bước 3: Lưu tài liệu hoàn chỉnh trong TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");
```

Trong bước này, chúng tôi lưu tài liệu hoàn chỉnh ở định dạng TIFF bằng cách sử dụng`Save` phương thức và chỉ định đường dẫn đến tệp đầu ra có phần mở rộng`.tiff`.

## Bước 4: Định cấu hình tùy chọn sao lưu cho phạm vi trang

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
PageSet = new PageSet(new PageRange(0, 1)),
TiffCompression = TiffCompression.Ccitt4,
Resolution = 160
};
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn sao lưu cho phạm vi trang cụ thể. Chúng tôi tạo ra một cái mới`ImageSaveOptions` đối tượng chỉ định định dạng lưu mong muốn, ở đây là "Tiff" cho định dạng TIFF. Chúng tôi sử dụng`PageSet` để chỉ định phạm vi trang chúng tôi muốn trích xuất, ở đây từ trang 0 đến trang 1 (bao gồm). Chúng tôi cũng đặt nén TIFF thành`Ccitt4` và độ phân giải tới 160 dpi.

## Bước 5: Lưu phạm vi trang vào TIFF

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
```

 Ở bước cuối cùng này, chúng tôi lưu phạm vi trang được chỉ định ở định dạng TIFF bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra với`.tiff` tiện ích mở rộng, cùng với các tùy chọn lưu được chỉ định .

Bây giờ bạn có thể chạy mã nguồn để lấy một phạm vi trang cụ thể từ tài liệu của mình và lưu chúng dưới dạng tệp TIFF. Các tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithImageSaveOptions.MultipageTiff.tiff" cho toàn bộ tài liệu và "WorkingWithImageSaveOptions.GetTiffPageRange.tiff" cho phạm vi trang được chỉ định.

### Mã nguồn mẫu của Nhận phạm vi trang Tiff bằng Aspose.Words cho .NET

```csharp 

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

doc.Save(dataDir + "WorkingWithImageSaveOptions.MultipageTiff.tiff");



ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Tiff)
{
	PageSet = new PageSet(new PageRange(0, 1)), TiffCompression = TiffCompression.Ccitt4, Resolution = 160
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetTiffPageRange.tiff", saveOptions);
            
            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá chức năng lấy nhiều trang TIFF bằng Aspose.Words cho .NET. Chúng tôi đã học cách trích xuất một phạm vi trang cụ thể từ tài liệu và lưu chúng dưới dạng tệp TIFF.

Tính năng này hữu ích khi bạn chỉ muốn trích xuất một số trang nhất định từ tài liệu và lưu chúng ở định dạng hình ảnh tiêu chuẩn như TIFF. Bạn cũng có thể tùy chỉnh các tùy chọn nén và độ phân giải để có được tệp TIFF chất lượng tốt nhất.

Aspose.Words for .NET cung cấp nhiều tính năng nâng cao để thao tác và tạo tài liệu. Nhận một phạm vi trang TIFF là một trong nhiều công cụ mạnh mẽ mà nó cung cấp cho bạn.

Vui lòng tích hợp chức năng này vào các dự án Aspose.Words for .NET của bạn để trích xuất và lưu các phạm vi trang cụ thể từ tài liệu của bạn ở định dạng TIFF.