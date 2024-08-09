---
title: Gọi lại lưu trang
linktitle: Gọi lại lưu trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách lưu từng trang của tài liệu Word dưới dạng hình ảnh PNG riêng biệt bằng Aspose.Words cho .NET với hướng dẫn từng bước chi tiết của chúng tôi.
type: docs
weight: 10
url: /vi/net/programming-with-imagesaveoptions/page-saving-callback/
---
## Giới thiệu

Này! Bạn đã bao giờ cảm thấy cần phải lưu từng trang của tài liệu Word dưới dạng hình ảnh riêng biệt chưa? Có thể bạn muốn chia nhỏ một báo cáo lớn thành các hình ảnh trực quan dễ hiểu hoặc có thể bạn cần tạo hình thu nhỏ để xem trước. Dù lý do của bạn là gì, việc sử dụng Aspose.Words cho .NET sẽ khiến công việc này trở nên dễ dàng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thiết lập lệnh gọi lại lưu trang để lưu từng trang của tài liệu dưới dạng hình ảnh PNG riêng lẻ. Hãy đi sâu vào ngay!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET: Nếu bạn chưa có, hãy tải xuống và cài đặt nó từ[đây](https://releases.aspose.com/words/net/).
2. Visual Studio: Mọi phiên bản đều hoạt động nhưng tôi sẽ sử dụng Visual Studio 2019 cho hướng dẫn này.
3. Kiến thức cơ bản về C#: Bạn sẽ cần hiểu biết cơ bản về C# để theo dõi.

## Nhập không gian tên

Đầu tiên, chúng ta cần nhập các không gian tên cần thiết. Điều này giúp chúng ta truy cập vào các lớp và phương thức được yêu cầu mà không cần phải gõ toàn bộ không gian tên mỗi lần.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Được rồi, hãy bắt đầu bằng cách xác định đường dẫn đến thư mục tài liệu của bạn. Đây là nơi chứa tài liệu Word đầu vào của bạn và là nơi lưu hình ảnh đầu ra.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu của bạn

Tiếp theo, chúng tôi sẽ tải tài liệu bạn muốn xử lý. Đảm bảo tài liệu của bạn ("Rendering.docx") nằm trong thư mục được chỉ định.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu hình ảnh

Chúng ta cần cấu hình các tùy chọn để lưu hình ảnh. Trong trường hợp này, chúng tôi đang lưu các trang dưới dạng tệp PNG.

```csharp
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
    PageSavingCallback = new HandlePageSavingCallback()
};
```

 Đây,`PageSet` chỉ định phạm vi trang cần lưu và`PageSavingCallback` trỏ đến lớp gọi lại tùy chỉnh của chúng tôi.

## Bước 4: Triển khai lệnh gọi lại lưu trang

Bây giờ, hãy triển khai lớp gọi lại để xử lý cách lưu từng trang.

```csharp
private class HandlePageSavingCallback : IPageSavingCallback
{
    public void PageSaving(PageSavingArgs args)
    {
        args.PageFileName = string.Format(dataDir + "Page_{0}.png", args.PageIndex);
    }
}
```

 Lớp này thực hiện các`IPageSavingCallback` giao diện và trong`PageSaving` phương pháp này, chúng tôi xác định mẫu đặt tên cho từng trang đã lưu.

## Bước 5: Lưu tài liệu dưới dạng hình ảnh

Cuối cùng, chúng tôi lưu tài liệu bằng các tùy chọn đã định cấu hình.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

## Phần kết luận

Và bạn có nó! Bạn đã thiết lập thành công lệnh gọi lại lưu trang để lưu từng trang của tài liệu Word dưới dạng hình ảnh PNG riêng biệt bằng cách sử dụng Aspose.Words for .NET. Kỹ thuật này cực kỳ hữu ích cho nhiều ứng dụng khác nhau, từ tạo bản xem trước trang đến tạo hình ảnh trang riêng lẻ cho báo cáo. 

Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Tôi có thể lưu trang ở định dạng khác ngoài PNG không?  
 Có, bạn có thể lưu trang ở các định dạng khác nhau như JPEG, BMP và TIFF bằng cách thay đổi`SaveFormat` TRONG`ImageSaveOptions`.

### Nếu tôi chỉ muốn lưu các trang cụ thể thì sao?  
 Bạn có thể chỉ định các trang bạn muốn lưu bằng cách điều chỉnh`PageSet` tham số trong`ImageSaveOptions`.

### Có thể tùy chỉnh chất lượng hình ảnh?  
 Tuyệt đối! Bạn có thể đặt thuộc tính như`ImageSaveOptions.JpegQuality` để kiểm soát chất lượng của hình ảnh đầu ra.

### Làm cách nào tôi có thể xử lý các tài liệu lớn một cách hiệu quả?  
Đối với các tài liệu lớn, hãy cân nhắc việc xử lý các trang theo đợt để quản lý việc sử dụng bộ nhớ một cách hiệu quả.

### Tôi có thể tìm thêm thông tin về Aspose.Words cho .NET ở đâu?  
 Kiểm tra[tài liệu](https://reference.aspose.com/words/net/) để có hướng dẫn và ví dụ toàn diện.