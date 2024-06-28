---
title: Định dạng thước kẻ ngang trong tài liệu Word
linktitle: Định dạng thước kẻ ngang trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn các quy tắc ngang có thể tùy chỉnh trong tài liệu Word bằng Aspose.Words cho .NET. Tăng cường tự động hóa tài liệu của bạn.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/horizontal-rule-format/
---
## Giới thiệu

Trong lĩnh vực phát triển .NET, việc thao tác và định dạng tài liệu Word theo chương trình có thể là một nhiệm vụ khó khăn. May mắn thay, Aspose.Words for .NET cung cấp một giải pháp mạnh mẽ, trao quyền cho các nhà phát triển tự động hóa việc tạo, chỉnh sửa và quản lý tài liệu một cách dễ dàng. Bài viết này đi sâu vào một trong những tính năng cần thiết: chèn thước ngang vào văn bản Word. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu với Aspose.Words, việc thành thạo khả năng này sẽ nâng cao quá trình tạo tài liệu của bạn.

## Điều kiện tiên quyết

Trước khi đi sâu vào triển khai các quy tắc theo chiều ngang bằng Aspose.Words cho .NET, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Visual Studio: Cài đặt Visual Studio IDE để phát triển .NET.
- Aspose.Words for .NET: Tải xuống và cài đặt Aspose.Words cho .NET từ[đây](https://releases.aspose.com/words/net/).
- Kiến thức cơ bản về C#: Làm quen với các kiến thức cơ bản về ngôn ngữ lập trình C#.
-  Lớp DocumentBuilder: Hiểu biết về`DocumentBuilder` lớp trong Aspose.Words để thao tác tài liệu.

## Nhập không gian tên

Để bắt đầu, hãy nhập các vùng tên cần thiết trong dự án C# của bạn:

```csharp
using Aspose.Words;
using System.Drawing;
```

Các không gian tên này cung cấp quyền truy cập vào các lớp Aspose.Words để thao tác tài liệu và các lớp .NET tiêu chuẩn để xử lý màu sắc.

Hãy chia nhỏ quá trình thêm quy tắc ngang trong tài liệu Word bằng Aspose.Words cho .NET thành các bước toàn diện:

## Bước 1: Khởi tạo DocumentBuilder và Đặt thư mục

 Đầu tiên, khởi tạo một`DocumentBuilder` đối tượng và đặt đường dẫn thư mục nơi tài liệu sẽ được lưu.

```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY_PATH";
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Chèn thước ngang

 Sử dụng`InsertHorizontalRule()` phương pháp của`DocumentBuilder` class để thêm quy tắc ngang.

```csharp
Shape shape = builder.InsertHorizontalRule();
```

## Bước 3: Tùy chỉnh định dạng quy tắc ngang

 Truy cập`HorizontalRuleFormat` thuộc tính của hình được chèn để tùy chỉnh hình thức của đường ngang.

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

- Căn chỉnh: Chỉ định căn chỉnh của quy tắc ngang (`HorizontalRuleAlignment.Center` trong ví dụ này).
- widthPercent: Đặt chiều rộng của quy tắc ngang theo tỷ lệ phần trăm của chiều rộng trang (trong ví dụ này là 70%).
- Chiều cao: Xác định chiều cao của thước ngang theo điểm (trong ví dụ này là 3 điểm).
- Color: Đặt màu của thước ngang (`Color.Blue` trong ví dụ này).
- NoShade: Chỉ định xem quy tắc ngang có nên có bóng hay không (`true` trong ví dụ này).

## Bước 4: Lưu tài liệu

 Cuối cùng, lưu tài liệu đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

```csharp
builder.Document.Save(dataDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

## Phần kết luận

Nắm vững cách chèn quy tắc ngang trong tài liệu Word bằng Aspose.Words for .NET sẽ nâng cao khả năng tự động hóa tài liệu của bạn. Bằng cách tận dụng tính linh hoạt và sức mạnh của Aspose.Words, các nhà phát triển có thể hợp lý hóa quy trình tạo và định dạng tài liệu một cách hiệu quả.

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ để làm việc với các tài liệu Word theo chương trình trong các ứng dụng .NET.

### Làm cách nào tôi có thể tải xuống Aspose.Words cho .NET?
 Bạn có thể tải xuống Aspose.Words cho .NET từ[đây](https://releases.aspose.com/words/net/).

### Tôi có thể tùy chỉnh giao diện của các quy tắc ngang trong Aspose.Words không?
Có, bạn có thể tùy chỉnh các khía cạnh khác nhau như căn chỉnh, chiều rộng, chiều cao, màu sắc và bóng của các quy tắc ngang bằng Aspose.Words.

### Aspose.Words có phù hợp để xử lý tài liệu cấp doanh nghiệp không?
Có, Aspose.Words được sử dụng rộng rãi trong môi trường doanh nghiệp nhờ khả năng thao tác tài liệu mạnh mẽ.

### Tôi có thể nhận hỗ trợ cho Aspose.Words cho .NET ở đâu?
 Để được hỗ trợ và tham gia cộng đồng, hãy truy cập[Diễn đàn Aspose.Words](https://forum.aspose.com/c/words/8).
