---
title: Mã nội tuyến
linktitle: Mã nội tuyến
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách áp dụng kiểu mã nội tuyến trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn này bao gồm các dấu backticks đơn và nhiều backticks để định dạng mã.
type: docs
weight: 10
url: /vi/net/working-with-markdown/inline-code/
---
## Giới thiệu

Nếu bạn đang tạo hoặc thao tác các tài liệu Word theo chương trình, bạn có thể cần định dạng văn bản cho giống với mã. Cho dù đó là tài liệu hay đoạn mã trong báo cáo, Aspose.Words for .NET đều cung cấp một cách mạnh mẽ để xử lý kiểu dáng văn bản. Trong hướng dẫn này, chúng ta sẽ tập trung vào cách áp dụng các kiểu mã nội tuyến cho văn bản bằng Aspose.Words. Chúng ta sẽ khám phá cách xác định và sử dụng các kiểu tùy chỉnh cho một và nhiều dấu phẩy ngược, làm cho các đoạn mã nổi bật rõ ràng trong tài liệu của bạn.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET Library: Đảm bảo bạn đã cài đặt Aspose.Words trong môi trường .NET của mình. Bạn có thể tải nó xuống từ[Trang phát hành Aspose.Words cho .NET](https://releases.aspose.com/words/net/).

2. Kiến thức cơ bản về lập trình .NET: Hướng dẫn này giả định rằng bạn có hiểu biết cơ bản về lập trình C# và .NET.

3. Môi trường phát triển: Bạn nên thiết lập môi trường phát triển .NET, chẳng hạn như Visual Studio, nơi bạn có thể viết và thực thi mã C#.

## Nhập không gian tên

Để bắt đầu sử dụng Aspose.Words trong dự án của bạn, bạn sẽ cần nhập các vùng tên cần thiết. Đây là cách bạn làm điều đó:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Hãy chia quy trình thành các bước rõ ràng:

## Bước 1: Khởi tạo Document và DocumentBuilder

 Đầu tiên bạn cần tạo một tài liệu mới và một`DocumentBuilder` ví dụ. các`DocumentBuilder`lớp giúp bạn thêm nội dung và định dạng nó trong tài liệu Word.

```csharp
// Khởi tạo DocumentBuilder bằng Tài liệu mới.
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Thêm kiểu mã nội tuyến bằng một backtick

Trong bước này, chúng ta sẽ xác định kiểu cho mã nội tuyến bằng một dấu tích ngược duy nhất. Kiểu này sẽ định dạng văn bản trông giống như mã nội tuyến.

### Xác định phong cách

```csharp
// Xác định kiểu ký tự mới cho mã nội tuyến bằng một dấu tích ngược.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
inlineCode1BackTicks.Font.Name = "Courier New"; // Một phông chữ điển hình cho mã.
inlineCode1BackTicks.Font.Size = 10.5; // Cỡ chữ cho mã nội tuyến.
inlineCode1BackTicks.Font.Color = System.Drawing.Color.Blue; // Màu văn bản mã.
inlineCode1BackTicks.Font.Bold = true; // Làm đậm văn bản mã.
```

### Áp dụng kiểu

Bây giờ, bạn có thể áp dụng kiểu này cho văn bản trong tài liệu của mình.

```csharp
// Sử dụng DocumentBuilder để chèn văn bản có kiểu mã nội tuyến.
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");
```

## Bước 3: Thêm kiểu mã nội tuyến với ba dấu backticks

Tiếp theo, chúng tôi sẽ xác định kiểu cho mã nội tuyến có ba dấu kiểm ngược, thường được sử dụng cho các khối mã nhiều dòng.

### Xác định phong cách

```csharp
// Xác định kiểu ký tự mới cho mã nội tuyến có ba dấu phẩy ngược.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
inlineCode3BackTicks.Font.Name = "Courier New"; // Phông chữ nhất quán cho mã.
inlineCode3BackTicks.Font.Size = 10.5; // Cỡ chữ cho khối mã.
inlineCode3BackTicks.Font.Color = System.Drawing.Color.Green; //Màu sắc khác nhau cho tầm nhìn.
inlineCode3BackTicks.Font.Bold = true; // Giữ nó đậm để nhấn mạnh.
```

### Áp dụng kiểu

Áp dụng kiểu này cho văn bản để định dạng nó dưới dạng khối mã nhiều dòng.

```csharp
// Áp dụng kiểu cho khối mã.
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```

## Phần kết luận

Việc định dạng văn bản dưới dạng mã nội tuyến trong tài liệu Word bằng Aspose.Words cho .NET rất đơn giản khi bạn biết các bước. Bằng cách xác định và áp dụng các kiểu tùy chỉnh với một hoặc nhiều dấu gạch ngang ngược, bạn có thể làm cho đoạn mã của mình nổi bật một cách rõ ràng. Phương pháp này đặc biệt hữu ích cho tài liệu kỹ thuật hoặc bất kỳ tài liệu nào mà khả năng đọc mã là cần thiết.

Hãy thoải mái thử nghiệm các kiểu và tùy chọn định dạng khác nhau để phù hợp nhất với nhu cầu của bạn. Aspose.Words cung cấp tính linh hoạt cao, cho phép bạn tùy chỉnh giao diện tài liệu của mình ở mức độ lớn.

## Câu hỏi thường gặp

### Tôi có thể sử dụng các phông chữ khác nhau cho kiểu mã nội tuyến không?
Có, bạn có thể sử dụng bất kỳ phông chữ nào phù hợp với nhu cầu của mình. Các phông chữ như "Courier New" thường được sử dụng cho mã do tính chất đơn cách của chúng.

### Làm cách nào để thay đổi màu của văn bản mã nội tuyến?
 Bạn có thể thay đổi màu sắc bằng cách thiết lập`Font.Color` thuộc tính của phong cách cho bất kỳ`System.Drawing.Color`.

### Tôi có thể áp dụng nhiều kiểu cho cùng một văn bản không?
Trong Aspose.Words, bạn chỉ có thể áp dụng một kiểu mỗi lần. Nếu bạn cần kết hợp các kiểu, hãy cân nhắc việc tạo một kiểu mới kết hợp tất cả các định dạng mong muốn.

### Làm cách nào để áp dụng kiểu cho văn bản hiện có trong tài liệu?
 Để áp dụng kiểu cho văn bản hiện có, trước tiên bạn cần chọn văn bản rồi áp dụng kiểu mong muốn bằng cách sử dụng`Font.Style` tài sản.

### Tôi có thể sử dụng Aspose.Words cho các định dạng tài liệu khác không?
Aspose.Words được thiết kế dành riêng cho tài liệu Word. Đối với các định dạng khác, bạn có thể cần sử dụng các thư viện khác nhau hoặc chuyển đổi tài liệu sang định dạng tương thích.