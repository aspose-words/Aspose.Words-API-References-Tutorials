---
title: Mã có rào chắn
linktitle: Mã có rào chắn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm chuỗi thông tin và mã có hàng rào vào tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước bao gồm. Nâng cao kỹ năng định dạng tài liệu của bạn.
type: docs
weight: 10
url: /vi/net/working-with-markdown/fenced-code/
---
## Giới thiệu

Này, anh bạn lập trình viên! Hôm nay, chúng ta sẽ đi sâu vào thế giới Aspose.Words dành cho .NET để nắm vững nghệ thuật thêm mã có hàng rào và mã có hàng rào với các chuỗi thông tin vào tài liệu Word của bạn. Hãy tưởng tượng tài liệu Word của bạn dưới dạng canvas và bạn, một nghệ sĩ, sắp vẽ với độ chính xác của một nhà phát triển dày dạn kinh nghiệm. Với Aspose.Words, bạn có khả năng nâng cao tài liệu của mình theo cách lập trình bằng các khối mã có cấu trúc, được định dạng, làm cho tài liệu kỹ thuật của bạn trở nên chuyên nghiệp và rõ ràng.

## Điều kiện tiên quyết

Trước khi bắt đầu phần hướng dẫn, hãy đảm bảo bạn có mọi thứ mình cần:

- Kiến thức cơ bản về C#: Hiểu biết tổng quát về C# sẽ giúp bạn nắm bắt các khái niệm một cách nhanh chóng.
-  Aspose.Words for .NET: Bạn cần cài đặt Aspose.Words for .NET. Nếu bạn chưa có thì hãy lấy nó[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ IDE C# nào khác mà bạn cảm thấy thoải mái.

## Nhập không gian tên

Trước tiên, bạn cần nhập các không gian tên cần thiết. Điều này giống như thu thập tất cả các công cụ của bạn trước khi bắt đầu một dự án.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

Bây giờ, hãy chia nhỏ quá trình này từng bước một.

## Bước 1: Thiết lập dự án của bạn

Trước khi có thể tạo các khối mã có định dạng đẹp, đẹp mắt trong tài liệu Word, chúng ta cần thiết lập một dự án mới trong Visual Studio.

1. Tạo một dự án mới: Mở Visual Studio và tạo Ứng dụng bảng điều khiển C# mới.
2. Thêm tài liệu tham khảo Aspose.Words: Cài đặt Aspose.Words thông qua Trình quản lý gói NuGet. Bạn có thể thực hiện việc này bằng cách nhấp chuột phải vào dự án của mình trong Solution Explorer, chọn "Quản lý gói NuGet" và tìm kiếm Aspose.Words.

## Bước 2: Khởi tạo DocumentBuilder

Bây giờ dự án của bạn đã được thiết lập, hãy khởi tạo DocumentBuilder, đây sẽ là công cụ chính của chúng ta để thêm nội dung vào tài liệu Word.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 3: Tạo kiểu cho mã có rào chắn

Để thêm mã rào chắn, trước tiên chúng ta cần tạo một style. Hãy coi điều này như việc đặt chủ đề cho khối mã của chúng ta.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Bước 4: Thêm mã có rào chắn vào tài liệu

Với phong cách đã sẵn sàng, giờ đây chúng ta có thể thêm khối mã có rào chắn vào tài liệu.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## Bước 5: Tạo kiểu cho mã có rào chắn bằng chuỗi thông tin

Đôi khi, bạn có thể muốn chỉ định ngôn ngữ lập trình hoặc thêm thông tin bổ sung vào khối mã của mình. Hãy tạo ra một phong cách cho điều đó.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Bước 6: Thêm mã có rào chắn với chuỗi thông tin vào tài liệu

Bây giờ, hãy thêm một khối mã có hàng rào với một chuỗi thông tin để cho biết đó là mã C#.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## Phần kết luận

Chúc mừng! Bạn vừa thêm các khối mã có hàng rào và mã có hàng rào với các chuỗi thông tin vào tài liệu Word của mình bằng cách sử dụng Aspose.Words cho .NET. Đây chỉ là phần nổi của tảng băng chìm. Với Aspose.Words, bạn có thể tự động hóa và nâng cao quá trình xử lý tài liệu của mình lên một tầm cao mới. Hãy tiếp tục khám phá và viết mã vui vẻ!

## Câu hỏi thường gặp

### Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo, thao tác và chuyển đổi tài liệu Word theo chương trình.

### Tôi có thể sử dụng Aspose.Words với các ngôn ngữ lập trình khác không?
Aspose.Words chủ yếu hỗ trợ các ngôn ngữ .NET, nhưng có sẵn các phiên bản cho Java, Python và các ngôn ngữ khác.

### Aspose.Words có được sử dụng miễn phí không?
 Aspose.Words là một sản phẩm thương mại nhưng bạn có thể tải xuống bản dùng thử miễn phí[đây](https://releases.aspose.com/)để khám phá các tính năng của nó.

### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Words?
 Bạn có thể nhận được hỗ trợ từ cộng đồng và nhà phát triển Aspose[đây](https://forum.aspose.com/c/words/8).

### Aspose.Words cung cấp những tính năng nào khác?
Aspose.Words cung cấp nhiều tính năng bao gồm chuyển đổi tài liệu, tạo tài liệu dựa trên mẫu, báo cáo và nhiều tính năng khác.