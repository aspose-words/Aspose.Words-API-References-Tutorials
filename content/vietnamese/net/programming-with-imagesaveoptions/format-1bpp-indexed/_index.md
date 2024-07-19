---
title: Định dạng 1Bpp được lập chỉ mục
linktitle: Định dạng 1Bpp được lập chỉ mục
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách định dạng hình ảnh trong 1 bpp được lập chỉ mục bằng Aspose.Words cho .NET. Hướng dẫn đầy đủ về hình ảnh có độ sâu màu thấp.
type: docs
weight: 10
url: /vi/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp cho chức năng "Định dạng 1Bpp được lập chỉ mục" với Aspose.Words cho .NET. Tính năng này cho phép bạn định dạng hình ảnh trong tài liệu ở định dạng PNG với độ sâu màu 1 bit trên mỗi pixel (1 bpp) và chế độ màu được lập chỉ mục.

## Bước 1: Thiết lập môi trường

Trước khi bắt đầu, hãy đảm bảo bạn đã thiết lập môi trường phát triển của mình với Aspose.Words for .NET. Đảm bảo bạn đã thêm các tham chiếu cần thiết và nhập các không gian tên thích hợp.

## Bước 2: Tải tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Ở bước này, chúng ta tải tài liệu bằng cách sử dụng`Document` phương thức và chuyển đường dẫn đến tệp DOCX để tải.

## Bước 3: Định cấu hình tùy chọn sao lưu ảnh

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(1),
     ImageColorMode = ImageColorMode.BlackAndWhite,
     PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn sao lưu cho hình ảnh. Chúng tôi tạo ra một cái mới`ImageSaveOptions`đối tượng chỉ định định dạng lưu mong muốn, ở đây "Png" cho định dạng PNG. Chúng tôi cũng xác định trang cần đưa vào hình ảnh, chế độ màu đen trắng và định dạng pixel 1 bpp được lập chỉ mục.

## Bước 4: Sao lưu hình ảnh

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

 Ở bước cuối cùng này, chúng tôi lưu hình ảnh tài liệu ở định dạng PNG bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra, cùng với các tùy chọn lưu được chỉ định.

Bây giờ bạn có thể chạy mã nguồn để định dạng hình ảnh tài liệu ở định dạng PNG với độ sâu màu được lập chỉ mục là 1 bpp. Tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithImageSaveOptions.Format1BppIndexed.Png".

### Mã nguồn mẫu cho Định dạng 1Bpp Được lập chỉ mục bằng Aspose.Words cho .NET

```csharp 
 
			 // Đường dẫn đến thư mục tài liệu của bạn
			 string dataDir = "YOUR DOCUMENT DIRECTORY"; 
            
            Document doc = new Document(dataDir + "Rendering.docx");

            ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
            {
                PageSet = new PageSet(1),
                ImageColorMode = ImageColorMode.BlackAndWhite,
                PixelFormat = ImagePixelFormat.Format1bppIndexed
            };

            doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
            
        
```

### Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá tính năng định dạng 1Bpp Indexed với Aspose.Words cho .NET. Chúng tôi đã tìm hiểu cách định dạng hình ảnh trong tài liệu ở định dạng PNG với độ sâu màu 1 bit trên mỗi pixel (1 bpp) và chế độ màu được lập chỉ mục.

Tính năng này hữu ích khi bạn muốn có được hình ảnh có độ sâu màu thấp và kích thước tệp nhỏ. Định dạng được lập chỉ mục 1Bpp cho phép hình ảnh được thể hiện bằng bảng màu được lập chỉ mục, điều này có thể mang lại lợi ích cho một số ứng dụng cụ thể.

Aspose.Words for .NET cung cấp nhiều tính năng nâng cao để thao tác và tạo tài liệu. Định dạng được lập chỉ mục 1Bpp là một trong nhiều công cụ mạnh mẽ mà bạn có thể tùy ý sử dụng.