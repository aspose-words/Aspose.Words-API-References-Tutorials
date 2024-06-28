---
title: Gọi lại lưu trang
linktitle: Gọi lại lưu trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tùy chỉnh việc lưu trang tài liệu thành hình ảnh bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-imagesaveoptions/page-saving-callback/
---

Trong hướng dẫn này, chúng ta sẽ khám phá mã nguồn C# được cung cấp để sử dụng lệnh gọi lại lưu trang với các tùy chọn lưu hình ảnh Aspose.Words cho .NET. Tính năng này cho phép bạn thực hiện các hành động tùy chỉnh khi lưu từng trang của tài liệu dưới dạng hình ảnh.

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
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
     PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
     PageSavingCallback = new HandlePageSavingCallback()
};
```

 Trong bước này, chúng tôi định cấu hình các tùy chọn lưu hình ảnh bằng cách tạo một`ImageSaveOptions` sự vật. Chúng tôi chỉ định định dạng sao lưu mong muốn, ở đây "Png" cho định dạng PNG. Chúng tôi sử dụng`PageSet` để chỉ định phạm vi trang cần lưu, ở đây từ trang đầu tiên đến trang cuối cùng của tài liệu (`doc.PageCount - 1`). Chúng tôi cũng thiết lập`PageSavingCallback` đến một trường hợp của`HandlePageSavingCallback`, đây là một lớp tùy chỉnh để xử lý lệnh gọi lại lưu trang.

## Bước 4: Thực hiện gọi lại trang lưu

```csharp
public class HandlePageSavingCallback : IPageSavingCallback
{
     public void PageSaving(PageSavingArgs args)
     {
         // Thực hiện các hành động tùy chỉnh của bạn ở đây
         // Bạn có thể truy cập thông tin trang thông qua thuộc tính "args.PageIndex"
         // Bạn cũng có thể thay đổi tùy chọn lưu cho từng trang riêng lẻ.
     }
}
```

 Ở bước này, chúng ta thực hiện`HandlePageSavingCallback` lớp thực hiện các`IPageSavingCallback` giao diện. Bạn có thể tùy chỉnh lớp này bằng cách thêm các hành động cụ thể của mình vào`PageSaving` phương pháp. Bạn có thể truy cập thông tin trang thông qua`args.PageIndex` tài sản của`PageSavingArgs` đối tượng được truyền dưới dạng đối số.

## Bước 5: Lưu trang dưới dạng hình ảnh

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
```

 Ở bước cuối cùng này, chúng tôi lưu từng trang của tài liệu dưới dạng hình ảnh bằng cách sử dụng`Save` phương thức và chuyển đường dẫn đến tệp đầu ra bằng`.png` tiện ích mở rộng, cùng với các tùy chọn lưu được chỉ định.

Bây giờ bạn có thể chạy mã nguồn để thực hiện các hành động tùy chỉnh khi lưu từng trang của tài liệu dưới dạng hình ảnh. Tệp kết quả sẽ được lưu trong thư mục được chỉ định với tên "WorkingWithImageSaveOptions.PageSavingCallback.png".

### Mã nguồn mẫu cho Gọi lại lưu trang bằng Aspose.Words cho .NET


```csharp 
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY"; 


Document doc = new Document(dataDir + "Rendering.docx");

ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFormat.Png)
{
	PageSet = new PageSet(new PageRange(0, doc.PageCount - 1)),
	PageSavingCallback = new HandlePageSavingCallback()
};

doc.Save(dataDir + "WorkingWithImageSaveOptions.PageSavingCallback.png", imageSaveOptions);
        
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá chức năng gọi lại lưu trang với các tùy chọn lưu hình ảnh Aspose.Words cho .NET. Chúng tôi đã học cách thực hiện các hành động tùy chỉnh khi lưu từng trang của tài liệu dưới dạng hình ảnh.

Tính năng này hữu ích khi bạn muốn thực hiện các thao tác cụ thể trên từng trang khi chuyển đổi sang hình ảnh. Bạn có thể truy cập thông tin trang và sử dụng nó để tùy chỉnh các tùy chọn sao lưu hoặc thực hiện xử lý theo trang cụ thể khác.

Aspose.Words for .NET cung cấp nhiều tính năng nâng cao để thao tác và tạo tài liệu. Lời nhắc Lưu trang là một trong nhiều công cụ mạnh mẽ cung cấp cho bạn để tùy chỉnh quá trình lưu trang vào hình ảnh.