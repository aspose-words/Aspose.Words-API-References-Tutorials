---
title: Định dạng 1Bpp được lập chỉ mục
linktitle: Định dạng 1Bpp được lập chỉ mục
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chuyển đổi tài liệu Word thành hình ảnh được lập chỉ mục 1Bpp bằng Aspose.Words cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để chuyển đổi dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Giới thiệu

Bạn đã bao giờ tự hỏi làm thế nào để lưu tài liệu Word dưới dạng hình ảnh đen trắng chỉ bằng một vài dòng mã chưa? Vâng, bạn thật may mắn! Hôm nay, chúng ta sẽ đi sâu vào một thủ thuật nhỏ gọn gàng bằng cách sử dụng Aspose.Words cho .NET cho phép bạn chuyển đổi tài liệu của mình thành hình ảnh được lập chỉ mục 1Bpp. Định dạng này hoàn hảo cho một số loại lưu trữ, in ấn kỹ thuật số nhất định hoặc khi bạn cần tiết kiệm dung lượng. Chúng tôi sẽ chia nhỏ từng bước để làm cho nó dễ dàng như ăn bánh. Sẵn sàng để bắt đầu? Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng ta bắt tay vào việc, có một số thứ bạn cần chuẩn bị sẵn:

-  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện. bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển .NET: Visual Studio là một lựa chọn tốt, nhưng bạn có thể sử dụng bất kỳ môi trường nào mà bạn cảm thấy thoải mái.
- Kiến thức cơ bản về C#: Đừng lo lắng, chúng tôi sẽ nói đơn giản nhưng làm quen một chút với C# sẽ hữu ích.
- Tài liệu Word: Chuẩn bị sẵn một tài liệu Word mẫu để chuyển đổi.

## Nhập không gian tên

Trước tiên, chúng ta cần nhập các không gian tên cần thiết. Điều này rất quan trọng vì nó cho phép chúng ta truy cập các lớp và phương thức mà chúng ta cần từ Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Bạn sẽ cần chỉ định đường dẫn đến thư mục tài liệu của mình. Đây là nơi tài liệu Word của bạn được lưu trữ và hình ảnh được chuyển đổi sẽ được lưu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu Word

 Bây giờ, hãy tải tài liệu Word vào Aspose.Words`Document` sự vật. Đối tượng này đại diện cho file Word của bạn và cho phép bạn thao tác với nó.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu hình ảnh

 Tiếp theo chúng ta cần thiết lập`ImageSaveOptions`Đây là nơi phép thuật xảy ra. Chúng tôi sẽ định cấu hình nó để lưu hình ảnh ở định dạng PNG với chế độ màu được lập chỉ mục 1Bpp.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: Điều này chỉ định rằng chúng tôi muốn lưu tài liệu dưới dạng hình ảnh PNG.
- PageSet(1): Điều này cho biết chúng tôi chỉ chuyển đổi trang đầu tiên.
- ImageColorMode.BlackAndWhite: Điều này đặt hình ảnh thành đen trắng.
- ImagePixelFormat.Format1bppIndexed: Cái này đặt định dạng hình ảnh thành 1Bpp được lập chỉ mục.

## Bước 4: Lưu tài liệu dưới dạng hình ảnh

 Cuối cùng, chúng tôi lưu tài liệu dưới dạng hình ảnh bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Phần kết luận

Và bạn có nó! Chỉ với một vài dòng mã, bạn đã chuyển đổi tài liệu Word của mình thành hình ảnh được lập chỉ mục 1Bpp bằng Aspose.Words cho .NET. Phương pháp này cực kỳ hữu ích để tạo hình ảnh có độ tương phản cao, tiết kiệm không gian từ tài liệu của bạn. Giờ đây, bạn có thể dễ dàng tích hợp tính năng này vào các dự án và quy trình làm việc của mình. Chúc mừng mã hóa!

## Câu hỏi thường gặp

### Hình ảnh được lập chỉ mục 1Bpp là gì?
Hình ảnh được lập chỉ mục 1Bpp (1 Bit trên mỗi pixel) là định dạng hình ảnh đen trắng trong đó mỗi pixel được biểu thị bằng một bit duy nhất, 0 hoặc 1. Định dạng này rất tiết kiệm không gian.

### Tôi có thể chuyển đổi nhiều trang của tài liệu Word cùng một lúc không?
 Vâng, bạn có thể. Sửa đổi`PageSet` tài sản ở`ImageSaveOptions` để bao gồm nhiều trang hoặc toàn bộ tài liệu.

### Tôi có cần giấy phép để sử dụng Aspose.Words cho .NET không?
 Có, Aspose.Words for .NET yêu cầu giấy phép để có đầy đủ chức năng. Bạn có thể nhận được một[giấy phép tạm thời ở đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể chuyển đổi tài liệu Word của mình sang những định dạng hình ảnh nào khác?
 Aspose.Words hỗ trợ nhiều định dạng hình ảnh khác nhau bao gồm JPEG, BMP và TIFF. Đơn giản chỉ cần thay đổi`SaveFormat` trong`ImageSaveOptions`.

### Tôi có thể tìm thêm tài liệu về Aspose.Words cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu chi tiết về[Trang tài liệu Aspose.Words cho .NET](https://reference.aspose.com/words/net/).
