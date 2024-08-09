---
title: Nhận phạm vi trang Jpeg
linktitle: Nhận phạm vi trang Jpeg
second_title: API xử lý tài liệu Aspose.Words
description: Chuyển đổi các trang cụ thể của tài liệu Word sang JPEG bằng cài đặt tùy chỉnh bằng Aspose.Words cho .NET. Tìm hiểu cách điều chỉnh độ sáng, độ tương phản và độ phân giải theo từng bước.
type: docs
weight: 10
url: /vi/net/programming-with-imagesaveoptions/get-jpeg-page-range/
---
## Giới thiệu

Việc chuyển đổi tài liệu Word thành hình ảnh có thể cực kỳ hữu ích, cho dù bạn đang tạo hình thu nhỏ, xem trước tài liệu trực tuyến hay chia sẻ nội dung ở định dạng dễ truy cập hơn. Với Aspose.Words for .NET, bạn có thể dễ dàng chuyển đổi các trang cụ thể của tài liệu Word sang định dạng JPEG trong khi tùy chỉnh các cài đặt khác nhau như độ sáng, độ tương phản và độ phân giải. Chúng ta hãy đi sâu vào cách đạt được điều này từng bước một!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, bạn sẽ cần chuẩn bị sẵn một số thứ:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt Aspose.Words for .NET. bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Môi trường phát triển AC# như Visual Studio.
- Tài liệu mẫu: Một tài liệu Word để làm việc. Bạn có thể sử dụng bất kỳ tệp .docx nào cho hướng dẫn này.
- Kiến thức C# cơ bản: Làm quen với lập trình C#.

Khi bạn đã sẵn sàng những thứ này, hãy bắt đầu!

## Nhập không gian tên

Để sử dụng Aspose.Words cho .NET, bạn sẽ cần nhập các vùng tên cần thiết ở đầu mã của mình. Điều này đảm bảo bạn có quyền truy cập vào tất cả các lớp và phương thức cần thiết để thao tác tài liệu.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Bước 1: Tải tài liệu của bạn

Đầu tiên chúng ta cần tải tài liệu Word muốn chuyển đổi. Giả sử tài liệu của chúng tôi được đặt tên`Rendering.docx` và nằm trong thư mục được chỉ định bởi trình giữ chỗ`YOUR DOCUMENT DIRECTORY`.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Mã này khởi tạo đường dẫn đến tài liệu của bạn và tải nó vào Aspose.Words`Document` sự vật.

## Bước 2: Thiết lập ImageSaveOptions

 Tiếp theo, chúng ta sẽ thiết lập`ImageSaveOptions` để chỉ định cách chúng tôi muốn tạo JPEG. Điều này bao gồm cài đặt phạm vi trang, độ sáng, độ tương phản và độ phân giải của hình ảnh.

```csharp
ImageSaveOptions options = new ImageSaveOptions(SaveFormat.Jpeg);
options.PageSet = new PageSet(0); // Chỉ chuyển đổi trang đầu tiên
options.ImageBrightness = 0.3f;   // Đặt độ sáng
options.ImageContrast = 0.7f;     // Đặt độ tương phản
options.HorizontalResolution = 72f; // Đặt độ phân giải
```

## Bước 3: Lưu tài liệu dưới dạng JPEG

Cuối cùng, chúng tôi lưu tài liệu dưới dạng tệp JPEG bằng các cài đặt mà chúng tôi đã xác định.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.GetJpegPageRange.jpeg", options);
```

 Mã này lưu trang đầu tiên của`Rendering.docx` dưới dạng hình ảnh JPEG với cài đặt độ sáng, độ tương phản và độ phân giải được chỉ định.

## Phần kết luận

Và bạn có nó! Bạn đã chuyển đổi thành công một trang cụ thể của tài liệu Word thành hình ảnh JPEG với các cài đặt tùy chỉnh bằng Aspose.Words for .NET. Quá trình này có thể được điều chỉnh để phù hợp với nhiều nhu cầu khác nhau, cho dù bạn đang chuẩn bị hình ảnh cho trang web, tạo bản xem trước tài liệu hay hơn thế nữa.

## Câu hỏi thường gặp

### Tôi có thể chuyển đổi nhiều trang cùng một lúc không?
 Có, bạn có thể chỉ định một loạt trang bằng cách sử dụng`PageSet` tài sản ở`ImageSaveOptions`.

### Làm cách nào để điều chỉnh chất lượng hình ảnh?
 Bạn có thể điều chỉnh chất lượng của JPEG bằng cách sử dụng`JpegQuality` tài sản ở`ImageSaveOptions`.

### Tôi có thể lưu ở các định dạng hình ảnh khác không?
 Có, Aspose.Words hỗ trợ nhiều định dạng hình ảnh khác nhau như PNG, BMP và TIFF. Thay đổi`SaveFormat` TRONG`ImageSaveOptions` tương ứng.

### Có cách nào để xem trước hình ảnh trước khi lưu không?
Bạn sẽ cần phải triển khai cơ chế xem trước một cách riêng biệt vì Aspose.Words không cung cấp tính năng xem trước tích hợp sẵn.

### Làm cách nào để có được giấy phép tạm thời cho Aspose.Words?
 Bạn có thể yêu cầu một[giấy phép tạm thời ở đây](https://purchase.aspose.com/temporary-license/).