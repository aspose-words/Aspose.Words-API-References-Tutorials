---
title: Bật Tắt thay thế phông chữ
linktitle: Bật Tắt thay thế phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách bật hoặc tắt tính năng thay thế phông chữ trong tài liệu Word bằng Aspose.Words cho .NET. Đảm bảo tài liệu của bạn trông nhất quán trên tất cả các nền tảng.
type: docs
weight: 10
url: /vi/net/working-with-fonts/enable-disable-font-substitution/
---
## Giới thiệu

Bạn đã bao giờ rơi vào tình huống các phông chữ được chọn tỉ mỉ trong tài liệu Word của bạn bị thay thế khi xem trên máy tính khác chưa? Khó chịu phải không? Điều này xảy ra do thay thế phông chữ, một quá trình trong đó hệ thống thay thế phông chữ bị thiếu bằng phông chữ có sẵn. Nhưng đừng lo lắng! Với Aspose.Words for .NET, bạn có thể dễ dàng quản lý và kiểm soát việc thay thế phông chữ. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để bật hoặc tắt tính năng thay thế phông chữ trong tài liệu Word của bạn, đảm bảo tài liệu của bạn luôn trông giống như cách bạn muốn.

## Điều kiện tiên quyết

Trước khi đi sâu vào các bước, hãy đảm bảo bạn có mọi thứ bạn cần:

-  Aspose.Words for .NET: Tải phiên bản mới nhất[đây](https://releases.aspose.com/words/net/).
- Visual Studio: Bất kỳ phiên bản nào hỗ trợ .NET.
- Kiến thức cơ bản về C#: Điều này sẽ giúp bạn theo dõi các ví dụ mã hóa.

## Nhập không gian tên

Để bắt đầu, hãy đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án của mình. Thêm những thứ này vào đầu tệp C# của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Bây giờ, hãy chia quy trình thành các bước đơn giản, dễ quản lý.

## Bước 1: Thiết lập dự án của bạn

Đầu tiên, thiết lập một dự án mới trong Visual Studio và thêm một tham chiếu đến thư viện Aspose.Words cho .NET. Nếu bạn chưa có, hãy tải xuống từ[trang web giả định](https://releases.aspose.com/words/net/).

## Bước 2: Tải tài liệu của bạn

Tiếp theo, tải tài liệu bạn muốn làm việc. Đây là cách bạn làm điều đó:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn. Mã này tải tài liệu vào bộ nhớ để bạn có thể thao tác với nó.

## Bước 3: Định cấu hình cài đặt phông chữ

 Bây giờ, hãy tạo một`FontSettings` đối tượng để quản lý cài đặt thay thế phông chữ:

```csharp
FontSettings fontSettings = new FontSettings();
```

## Bước 4: Đặt thay thế phông chữ mặc định

Đặt thay thế phông chữ mặc định thành phông chữ bạn chọn. Phông chữ này sẽ được sử dụng nếu phông chữ gốc không có sẵn:

```csharp
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

Trong ví dụ này, chúng tôi đang sử dụng Arial làm phông chữ mặc định.

## Bước 5: Vô hiệu hóa thay thế thông tin phông chữ

Để tắt tính năng thay thế thông tin phông chữ, ngăn hệ thống thay thế các phông chữ bị thiếu bằng các phông chữ có sẵn, hãy sử dụng mã sau:

```csharp
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
```

## Bước 6: Áp dụng cài đặt phông chữ cho tài liệu

Bây giờ, hãy áp dụng các cài đặt này cho tài liệu của bạn:

```csharp
doc.FontSettings = fontSettings;
```

## Bước 7: Lưu tài liệu của bạn

Cuối cùng, lưu tài liệu đã sửa đổi của bạn. Bạn có thể lưu nó ở bất kỳ định dạng nào bạn thích. Đối với hướng dẫn này, chúng tôi sẽ lưu nó dưới dạng PDF:

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```

## Phần kết luận

Và bạn có nó! Bằng cách làm theo các bước này, bạn có thể dễ dàng kiểm soát việc thay thế phông chữ trong tài liệu Word của mình bằng Aspose.Words for .NET. Điều này đảm bảo tài liệu của bạn duy trì giao diện như mong muốn, bất kể chúng được xem ở đâu.

## Câu hỏi thường gặp

### Tôi có thể sử dụng phông chữ khác ngoài Arial để thay thế không?

 Tuyệt đối! Bạn có thể chỉ định bất kỳ phông chữ nào có sẵn trên hệ thống của mình bằng cách thay đổi tên phông chữ trong`DefaultFontName` tài sản.

### Điều gì xảy ra nếu phông chữ mặc định được chỉ định không có sẵn?

Nếu phông chữ mặc định không có sẵn, Aspose.Words sẽ sử dụng cơ chế dự phòng hệ thống để tìm phông chữ thay thế thích hợp.

### Tôi có thể bật lại tính năng thay thế phông chữ sau khi tắt nó không?

 Có, bạn có thể chuyển đổi`Enabled` tài sản của`FontInfoSubstitution` quay lại`true` nếu bạn muốn bật lại tính năng thay thế phông chữ.

### Có cách nào để kiểm tra phông chữ nào đang được thay thế không?

Có, Aspose.Words cung cấp các phương pháp ghi nhật ký và theo dõi việc thay thế phông chữ, cho phép bạn xem phông chữ nào đang được thay thế.

### Tôi có thể sử dụng phương pháp này cho các định dạng tài liệu khác ngoài DOCX không?

Chắc chắn! Aspose.Words hỗ trợ nhiều định dạng khác nhau và bạn có thể áp dụng các cài đặt phông chữ này cho bất kỳ định dạng được hỗ trợ nào.