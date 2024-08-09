---
title: Thêm tiền tố tên lớp Css
linktitle: Thêm tiền tố tên lớp Css
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm tiền tố tên lớp CSS khi lưu tài liệu Word dưới dạng HTML bằng Aspose.Words cho .NET. Bao gồm hướng dẫn từng bước, đoạn mã và câu hỏi thường gặp.
type: docs
weight: 10
url: /vi/net/programming-with-htmlsaveoptions/add-css-class-name-prefix/
---
## Giới thiệu

Chào mừng! Nếu bạn đang tìm hiểu thế giới của Aspose.Words dành cho .NET, bạn sẽ được thưởng thức. Hôm nay, chúng ta sẽ khám phá cách thêm tiền tố tên lớp CSS khi lưu tài liệu Word dưới dạng HTML bằng Aspose.Words cho .NET. Tính năng này cực kỳ tiện dụng khi bạn muốn tránh xung đột tên lớp trong tệp HTML của mình.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET: Nếu bạn chưa cài đặt nó,[tải nó ở đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ IDE C# nào khác.
-  Tài liệu Word: Chúng tôi sẽ sử dụng tài liệu có tên`Rendering.docx`. Đặt nó trong thư mục dự án của bạn.

## Nhập không gian tên

Trước tiên, hãy đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án C# của mình. Thêm những thứ này vào đầu tệp mã của bạn:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

Bây giờ, hãy đi sâu vào hướng dẫn từng bước!

## Bước 1: Thiết lập dự án của bạn

Trước khi chúng ta có thể bắt đầu thêm tiền tố tên lớp CSS, hãy thiết lập dự án của chúng ta.

### Bước 1.1: Tạo một dự án mới

 Hãy khởi động Visual Studio của bạn và tạo dự án Ứng dụng Console mới. Đặt tên cho nó một cái gì đó hấp dẫn như`AsposeCssPrefixExample`.

### Bước 1.2: Thêm Aspose.Words cho .NET

Nếu bạn chưa có, hãy thêm Aspose.Words for .NET vào dự án của bạn thông qua NuGet. Chỉ cần mở Bảng điều khiển quản lý gói NuGet và chạy:

```bash
Install-Package Aspose.Words
```

Tuyệt vời! Bây giờ, chúng ta đã sẵn sàng để bắt đầu viết mã.

## Bước 2: Tải tài liệu của bạn

Điều đầu tiên chúng ta cần làm là tải tài liệu Word mà chúng ta muốn chuyển đổi sang HTML.

### Bước 2.1: Xác định đường dẫn tài liệu

 Thiết lập đường dẫn đến thư mục tài liệu của bạn. Vì mục đích của hướng dẫn này, giả sử tài liệu của bạn nằm trong thư mục có tên`Documents` trong thư mục dự án của bạn.

```csharp
string dataDir = @"C:\YourProject\Documents\";
```

### Bước 2.2: Tải tài liệu

Bây giờ, hãy tải tài liệu bằng Aspose.Words:

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu HTML

Tiếp theo, chúng ta cần định cấu hình các tùy chọn lưu HTML để bao gồm tiền tố tên lớp CSS.

### Bước 3.1: Tạo tùy chọn lưu HTML

 Khởi tạo`HtmlSaveOptions` đối tượng và đặt loại bảng định kiểu CSS thành`External`.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External
};
```

### Bước 3.2: Đặt tiền tố tên lớp CSS

 Bây giờ, hãy thiết lập`CssClassNamePrefix` property thành tiền tố mong muốn của bạn. Đối với ví dụ này, chúng tôi sẽ sử dụng`"pfx_"`.

```csharp
saveOptions.CssClassNamePrefix = "pfx_";
```

## Bước 4: Lưu tài liệu dưới dạng HTML

Cuối cùng, hãy lưu tài liệu dưới dạng tệp HTML với các tùy chọn đã định cấu hình của chúng tôi.


Chỉ định đường dẫn tệp HTML đầu ra và lưu tài liệu.

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html", saveOptions);
```

## Bước 5: Xác minh đầu ra

 Sau khi chạy dự án của bạn, hãy điều hướng đến`Documents` thư mục. Bạn nên tìm một tệp HTML có tên`WorkingWithHtmlSaveOptions.AddCssClassNamePrefix.html` . Mở tệp này trong trình soạn thảo văn bản hoặc trình duyệt để xác minh rằng các lớp CSS có tiền tố`pfx_`.

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn đã thêm thành công tiền tố tên lớp CSS vào đầu ra HTML của mình bằng Aspose.Words cho .NET. Tính năng đơn giản nhưng mạnh mẽ này có thể giúp bạn duy trì phong cách rõ ràng và không xung đột trong tài liệu HTML của mình.

## Câu hỏi thường gặp

### Tôi có thể sử dụng tiền tố khác nhau cho mỗi thao tác lưu không?
 Có, bạn có thể tùy chỉnh tiền tố mỗi lần lưu tài liệu bằng cách thay đổi`CssClassNamePrefix` tài sản.

### Phương pháp này có hỗ trợ CSS nội tuyến không?
 các`CssClassNamePrefix`thuộc tính hoạt động với CSS bên ngoài. Đối với CSS nội tuyến, bạn sẽ cần một cách tiếp cận khác.

### Làm cách nào tôi có thể bao gồm các tùy chọn lưu HTML khác?
 Bạn có thể cấu hình các thuộc tính khác nhau của`HtmlSaveOptions` để tùy chỉnh đầu ra HTML của bạn. Kiểm tra[tài liệu](https://reference.aspose.com/words/net/) để biết thêm chi tiết.

### Có thể lưu HTML vào một luồng không?
 Tuyệt đối! Bạn có thể lưu tài liệu vào một luồng bằng cách chuyển đối tượng luồng tới`Save` phương pháp.

### Làm cách nào để nhận được hỗ trợ nếu tôi gặp vấn đề?
 Bạn có thể nhận được sự hỗ trợ từ[diễn đàn giả định](https://forum.aspose.com/c/words/8).