---
title: Đặt thư mục phông chữ
linktitle: Đặt thư mục phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt thư mục phông chữ tùy chỉnh trong Aspose.Words cho .NET để đảm bảo tài liệu Word của bạn được hiển thị chính xác mà không bị thiếu phông chữ.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folder/
---
## Giới thiệu

Bạn đã bao giờ gặp phải vấn đề thiếu phông chữ khi làm việc với tài liệu Word trong ứng dụng .NET của mình chưa? Vâng, bạn không đơn độc. Đặt đúng thư mục phông chữ có thể giải quyết vấn đề này một cách liền mạch. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách đặt thư mục phông chữ bằng Aspose.Words cho .NET. Hãy đi sâu vào!

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

- Visual Studio được cài đặt trên máy của bạn
- .NET Framework được thiết lập
-  Aspose.Words cho thư viện .NET. Nếu chưa có, bạn có thể tải xuống từ[đây](https://releases.aspose.com/words/net/).

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết để hoạt động với Aspose.Words. Thêm các dòng sau vào đầu tệp mã của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Việc thiết lập thư mục phông chữ rất đơn giản nếu bạn làm theo các bước sau một cách cẩn thận.

## Bước 1: Xác định thư mục tài liệu

Trước bất cứ điều gì khác, hãy xác định đường dẫn đến thư mục tài liệu của bạn. Thư mục này sẽ chứa các tài liệu Word của bạn và các phông chữ bạn muốn sử dụng.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục của bạn.

## Bước 2: Khởi tạo FontSettings

 Bây giờ, bạn cần khởi tạo`FontSettings` sự vật. Đối tượng này cho phép bạn chỉ định các thư mục phông chữ tùy chỉnh.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Bước 3: Đặt thư mục phông chữ

 Sử dụng`SetFontsFolder` phương pháp của`FontSettings` đối tượng, hãy chỉ định thư mục nơi lưu trữ phông chữ tùy chỉnh của bạn.

```csharp
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

 Đây,`dataDir + "Fonts"` trỏ đến thư mục có tên "Phông chữ" trong thư mục tài liệu của bạn. Tham số thứ hai,`false`, chỉ ra rằng thư mục không đệ quy.

## Bước 4: Tạo LoadOptions

 Tiếp theo, tạo một thể hiện của`LoadOptions` lớp học. Lớp này sẽ giúp bạn tải tài liệu với các cài đặt phông chữ được chỉ định.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
```

## Bước 5: Tải tài liệu

 Cuối cùng, tải tài liệu Word bằng cách sử dụng`Document` lớp học và`LoadOptions` sự vật.

```csharp
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```

 Hãy chắc chắn rằng`"Rendering.docx"` là tên tài liệu Word của bạn. Bạn có thể thay thế nó bằng tên tập tin của bạn.

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn có thể dễ dàng đặt thư mục phông chữ tùy chỉnh trong Aspose.Words cho .NET, đảm bảo rằng tất cả phông chữ của bạn được hiển thị chính xác. Thiết lập đơn giản này có thể giúp bạn tránh khỏi nhiều rắc rối và làm cho tài liệu của bạn trông chính xác như bạn muốn.

## Câu hỏi thường gặp

### Tại sao tôi cần đặt thư mục phông chữ tùy chỉnh?
Việc đặt thư mục phông chữ tùy chỉnh sẽ đảm bảo rằng tất cả các phông chữ được sử dụng trong tài liệu Word của bạn đều được hiển thị chính xác, tránh các vấn đề về thiếu phông chữ.

### Tôi có thể đặt nhiều thư mục phông chữ không?
 Có, bạn có thể sử dụng`SetFontsFolders` phương pháp để chỉ định nhiều thư mục.

### Điều gì xảy ra nếu không tìm thấy phông chữ?
Aspose.Words sẽ cố gắng thay thế phông chữ bị thiếu bằng phông chữ tương tự từ phông chữ hệ thống.

### Aspose.Words có tương thích với .NET Core không?
Có, Aspose.Words hỗ trợ .NET Core cùng với .NET Framework.

### Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?
 Bạn có thể nhận được sự hỗ trợ từ[Diễn đàn hỗ trợ Aspose.Words](https://forum.aspose.com/c/words/8).