---
title: Nhận phạm vi trang Jpeg
linktitle: Nhận phạm vi trang Jpeg
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách lấy nhiều trang JPEG bằng Aspose.Words cho .NET. Hướng dẫn hoàn chỉnh để trích xuất hình ảnh tùy chỉnh.
type: docs
weight: 10
url: /vi/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---

Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp cho tính năng "Nhận phạm vi trang JPEG" với Aspose.Words cho .NET. Tính năng này cho phép bạn chuyển đổi một phạm vi trang cụ thể của tài liệu thành hình ảnh ở định dạng JPEG.

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
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options. PageSet = new PageSet(0);
options. ImageBrightness = 0.3f;
options. ImageContrast = 0.7f;
options. HorizontalResolution = 72f;
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn sao lưu cho hình ảnh. Chúng tôi tạo ra một cái mới`ImageSaveOptions` đối tượng chỉ định định dạng lưu mong muốn, ở đây là "Jpeg" cho định dạng JPEG. Chúng tôi cũng đặt phạm vi trang cần chuyển đổi bằng cách sử dụng`PageSet`sự vật. Cuối cùng, chúng ta điều chỉnh độ sáng và độ tương phản của hình ảnh bằng cách sử dụng`ImageBrightness`Và`ImageContrast` các thuộc tính tương ứng. Chúng tôi cũng thay đổi độ phân giải ngang bằng cách sử dụng`HorizontalResolution` tài sản.

## Bước 4: Sao lưu hình ảnh

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Ở bước cuối cùng này, chúng tôi lưu hình ảnh của phạm vi trang được chỉ định ở định dạng JPEG bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra, cùng với các tùy chọn lưu được chỉ định.

Bây giờ bạn có thể chạy mã nguồn để chuyển đổi một phạm vi trang cụ thể trong tài liệu của mình sang hình ảnh JPEG. Tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg".

### Mã nguồn mẫu cho Nhận phạm vi trang Jpeg bằng Aspose.Words For .NET

```csharp 
 // Đường dẫn đến thư mục tài liệu của bạn
 string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);

// Đặt "PageSet" thành "0" để chỉ chuyển đổi trang đầu tiên của tài liệu.
options.PageSet = new PageSet(0);

// Thay đổi độ sáng và độ tương phản của hình ảnh.
// Cả hai đều có thang điểm 0-1 và ở mức 0,5 theo mặc định.
options.ImageBrightness = 0.3f;
options.ImageContrast = 0.7f;

// Thay đổi độ phân giải ngang.
// Giá trị mặc định cho các thuộc tính này là 96,0, cho độ phân giải 96dpi.
options.HorizontalResolution = 72f;

doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
            
        
```

## Phần kết luận

Trong hướng dẫn này, chúng ta đã khám phá chức năng lấy phạm vi trang JPEG bằng Aspose.Words cho .NET. Chúng tôi đã học cách chuyển đổi một phạm vi trang cụ thể của tài liệu thành hình ảnh ở định dạng JPEG, đồng thời tùy chỉnh các tùy chọn lưu.

Tính năng này hữu ích khi bạn muốn trích xuất các trang cụ thể từ tài liệu và lưu chúng dưới dạng hình ảnh JPEG. Bạn cũng có thể điều chỉnh độ sáng, độ tương phản và độ phân giải ngang của hình ảnh để đạt được kết quả được cá nhân hóa.

Aspose.Words for .NET cung cấp nhiều tính năng nâng cao để thao tác và tạo tài liệu. Lấy một phạm vi trang JPEG là một trong nhiều công cụ mạnh mẽ mà nó cung cấp cho bạn.

Vui lòng tích hợp tính năng này vào các dự án Aspose.Words for .NET để có được hình ảnh JPEG chất lượng cao từ tài liệu của bạn.