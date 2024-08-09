---
title: Đặt mức độ ưu tiên của thư mục phông chữ
linktitle: Đặt mức độ ưu tiên của thư mục phông chữ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt mức độ ưu tiên của thư mục phông chữ trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn của chúng tôi đảm bảo tài liệu của bạn luôn hiển thị hoàn hảo.
type: docs
weight: 10
url: /vi/net/working-with-fonts/set-fonts-folders-with-priority/
---
## Giới thiệu

Trong thế giới thao tác tài liệu, việc đặt các thư mục phông chữ tùy chỉnh có thể tạo ra sự khác biệt lớn trong việc đảm bảo tài liệu của bạn hiển thị hoàn hảo, bất kể chúng được xem ở đâu. Hôm nay, chúng ta sẽ đi sâu vào cách bạn có thể đặt mức độ ưu tiên của các thư mục phông chữ trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn toàn diện này sẽ hướng dẫn bạn từng bước, giúp quá trình diễn ra suôn sẻ nhất có thể.

## Điều kiện tiên quyết

Trước khi bắt đầu, hãy đảm bảo rằng chúng ta có mọi thứ mình cần. Dưới đây là danh sách kiểm tra nhanh:

-  Aspose.Words for .NET: Bạn cần cài đặt thư viện này. Nếu bạn chưa có nó, bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Đảm bảo bạn có môi trường phát triển .NET hoạt động, như Visual Studio.
-  Thư mục tài liệu: Đảm bảo bạn có một thư mục cho tài liệu của mình. Đối với các ví dụ của chúng tôi, chúng tôi sẽ sử dụng`"YOUR DOCUMENT DIRECTORY"` làm trình giữ chỗ cho đường dẫn này.

## Nhập không gian tên

Trước tiên, chúng ta cần nhập các không gian tên cần thiết. Các không gian tên này rất cần thiết để truy cập các lớp và phương thức do Aspose.Words cung cấp.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Bây giờ, hãy chia nhỏ từng bước để đặt mức độ ưu tiên cho các thư mục phông chữ.

## Bước 1: Thiết lập nguồn phông chữ của bạn

Để bắt đầu, bạn sẽ muốn xác định nguồn phông chữ. Đây là nơi bạn cho Aspose.Words biết nơi tìm phông chữ. Bạn có thể chỉ định nhiều thư mục phông chữ và thậm chí đặt mức độ ưu tiên của chúng.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
    new SystemFontSource(), 
    new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

Trong ví dụ này, chúng tôi đang đặt hai nguồn phông chữ:
- SystemFontSource: Đây là nguồn phông chữ mặc định bao gồm tất cả các phông chữ được cài đặt trên hệ thống của bạn.
-  FolderFontSource: Đây là thư mục phông chữ tùy chỉnh nằm ở`C:\\MyFonts\\` . các`true` tham số chỉ định rằng thư mục này sẽ được quét đệ quy và`1` đặt mức độ ưu tiên của nó.

## Bước 2: Tải tài liệu của bạn

Tiếp theo, tải tài liệu bạn muốn làm việc. Đảm bảo tài liệu nằm trong thư mục được chỉ định của bạn.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

 Dòng mã này tải một tài liệu có tên`Rendering.docx` từ thư mục tài liệu của bạn.

## Bước 3: Lưu tài liệu của bạn với cài đặt phông chữ mới

Cuối cùng, lưu tài liệu của bạn. Khi bạn lưu tài liệu, Aspose.Words sẽ sử dụng cài đặt phông chữ bạn đã chỉ định.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

 Thao tác này sẽ lưu tài liệu dưới dạng PDF trong thư mục tài liệu của bạn với tên`WorkingWithFonts.SetFontsFoldersWithPriority.pdf`.

## Phần kết luận

Và bạn có nó! Bạn đã thiết lập thành công các thư mục phông chữ có mức độ ưu tiên bằng Aspose.Words cho .NET. Bằng cách chỉ định các thư mục phông chữ tùy chỉnh và mức độ ưu tiên, bạn có thể đảm bảo tài liệu của mình hiển thị nhất quán, bất kể chúng được xem ở đâu. Điều này đặc biệt hữu ích trong môi trường mà phông chữ cụ thể không được cài đặt theo mặc định.

## Câu hỏi thường gặp

### Tại sao tôi cần đặt thư mục phông chữ tùy chỉnh?
Việc đặt thư mục phông chữ tùy chỉnh sẽ đảm bảo rằng tài liệu của bạn hiển thị chính xác, ngay cả khi chúng sử dụng phông chữ không được cài đặt trên hệ thống nơi chúng đang được xem.

### Tôi có thể đặt nhiều thư mục phông chữ tùy chỉnh không?
Có, bạn có thể chỉ định nhiều thư mục phông chữ. Aspose.Words cho phép bạn đặt mức độ ưu tiên cho từng thư mục, đảm bảo rằng các phông chữ quan trọng nhất sẽ được tìm thấy trước tiên.

### Điều gì xảy ra nếu phông chữ bị thiếu trong tất cả các nguồn được chỉ định?
Nếu phông chữ bị thiếu trong tất cả các nguồn được chỉ định, Aspose.Words sẽ sử dụng phông chữ dự phòng để đảm bảo tài liệu vẫn có thể đọc được.

### Tôi có thể thay đổi mức độ ưu tiên của phông chữ hệ thống không?
Các phông chữ hệ thống luôn được bao gồm theo mặc định, nhưng bạn có thể đặt mức độ ưu tiên của chúng tương ứng với các thư mục phông chữ tùy chỉnh của mình.

### Có thể sử dụng đường dẫn mạng cho các thư mục phông chữ tùy chỉnh không?
Có, bạn có thể chỉ định đường dẫn mạng làm thư mục phông chữ tùy chỉnh, cho phép bạn tập trung tài nguyên phông chữ trên một vị trí mạng.