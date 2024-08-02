---
title: Thêm hình mờ văn bản với các tùy chọn cụ thể
linktitle: Thêm hình mờ văn bản với các tùy chọn cụ thể
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm hình mờ văn bản với các tùy chọn cụ thể vào tài liệu Word của bạn bằng Aspose.Words for .NET. Tùy chỉnh phông chữ, kích thước, màu sắc và bố cục một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## Giới thiệu

Hình mờ có thể là một sự bổ sung đầy phong cách và chức năng cho tài liệu Word của bạn, phục vụ các mục đích từ đánh dấu tài liệu là bí mật cho đến thêm dấu ấn cá nhân hóa. Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm hình mờ văn bản vào tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ đi sâu vào các tùy chọn cụ thể mà bạn có thể định cấu hình, chẳng hạn như họ phông chữ, cỡ chữ, màu sắc và bố cục. Cuối cùng, bạn sẽ có thể tùy chỉnh hình mờ của tài liệu để phù hợp với nhu cầu chính xác của mình. Vì vậy, hãy lấy trình soạn thảo mã của bạn và bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET Library: Bạn sẽ cần cài đặt thư viện Aspose.Words. Nếu bạn chưa làm như vậy, bạn có thể tải xuống từ[Liên kết tải xuống Aspose.Words](https://releases.aspose.com/words/net/).
2. Hiểu biết cơ bản về C#: Hướng dẫn này sẽ sử dụng C# làm ngôn ngữ lập trình. Việc nắm bắt cơ bản về cú pháp C# sẽ rất hữu ích.
3. Môi trường phát triển .NET: Đảm bảo bạn đã thiết lập môi trường phát triển (như Visual Studio), nơi bạn có thể tạo và chạy các ứng dụng .NET của mình.

## Nhập không gian tên

Để làm việc với Aspose.Words, bạn cần đưa các không gian tên cần thiết vào dự án của mình. Đây là những gì bạn cần nhập:

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## Bước 1: Thiết lập tài liệu của bạn

 Trước tiên, bạn cần tải tài liệu bạn muốn làm việc. Đối với hướng dẫn này, chúng tôi sẽ sử dụng một tài liệu mẫu có tên`Document.docx`. Hãy chắc chắn rằng tài liệu này tồn tại trong thư mục được chỉ định của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Trong bước này, bạn xác định thư mục chứa tài liệu của mình và tải nó vào một phiên bản của`Document` lớp học.

## Bước 2: Định cấu hình tùy chọn hình mờ

Tiếp theo, định cấu hình các tùy chọn cho hình mờ văn bản của bạn. Bạn có thể tùy chỉnh nhiều khía cạnh khác nhau, chẳng hạn như họ phông chữ, cỡ chữ, màu sắc và bố cục. Hãy thiết lập các tùy chọn này.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

Đây là những gì mỗi tùy chọn thực hiện:
- `FontFamily`: Chỉ định phông chữ của văn bản hình mờ.
- `FontSize`: Đặt kích thước của văn bản hình mờ.
- `Color`: Xác định màu của văn bản hình mờ.
- `Layout`Xác định hướng của hình mờ (ngang hoặc chéo).
- `IsSemitrasparent`: Đặt xem hình mờ có bán trong suốt hay không.

## Bước 3: Thêm văn bản hình mờ

Bây giờ, áp dụng hình mờ cho tài liệu của bạn bằng các tùy chọn đã định cấu hình trước đó. Trong bước này, bạn sẽ đặt văn bản hình mờ thành "Kiểm tra" và áp dụng các tùy chọn bạn đã xác định.

```csharp
doc.Watermark.SetText("Test", options);
```

Dòng mã này thêm hình mờ có nội dung "Kiểm tra" vào tài liệu, áp dụng các tùy chọn đã chỉ định.

## Bước 4: Lưu tài liệu

Cuối cùng, lưu tài liệu với hình mờ mới được áp dụng. Bạn có thể lưu nó bằng tên mới để tránh ghi đè lên tài liệu gốc.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

Đoạn mã này lưu tài liệu đã sửa đổi vào cùng thư mục với tên tệp mới.

## Phần kết luận

Thêm hình mờ văn bản vào tài liệu Word của bạn bằng Aspose.Words cho .NET là một quá trình đơn giản khi bạn chia nó thành các bước có thể quản lý được. Bằng cách làm theo hướng dẫn này, bạn đã học cách định cấu hình các tùy chọn hình mờ khác nhau, bao gồm phông chữ, kích thước, màu sắc, bố cục và độ trong suốt. Với những kỹ năng này, giờ đây bạn có thể tùy chỉnh tài liệu của mình để đáp ứng tốt hơn nhu cầu của mình hoặc để bao gồm các thông tin cần thiết như tính bảo mật hoặc thương hiệu.

 Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ thêm, vui lòng kiểm tra[Tài liệu Aspose.Words](https://reference.aspose.com/words/net/) hoặc ghé thăm[Diễn đàn hỗ trợ Aspose](https://forum.aspose.com/c/words/8) để được trợ giúp thêm.

## Câu hỏi thường gặp

### Tôi có thể sử dụng các phông chữ khác nhau cho hình mờ không?

 Có, bạn có thể chọn bất kỳ phông chữ nào được cài đặt trên hệ thống của mình bằng cách chỉ định`FontFamily` tài sản ở`TextWatermarkOptions`.

### Làm cách nào để thay đổi màu của hình mờ?

 Bạn có thể thay đổi màu của hình mờ bằng cách đặt`Color` tài sản ở`TextWatermarkOptions` cho bất kỳ`System.Drawing.Color` giá trị.

### Có thể thêm nhiều hình mờ vào một tài liệu không?

Aspose.Words hỗ trợ thêm một hình mờ cùng một lúc. Để thêm nhiều hình mờ, bạn cần tạo và áp dụng chúng một cách tuần tự.

### Tôi có thể điều chỉnh vị trí của hình mờ không?

 Các`WatermarkLayout`thuộc tính xác định hướng nhưng việc điều chỉnh vị trí chính xác không được hỗ trợ trực tiếp. Bạn có thể cần phải sử dụng các kỹ thuật khác để có được vị trí chính xác.

### Nếu tôi cần hình mờ bán trong suốt thì sao?

 Đặt`IsSemitrasparent`tài sản để`true` để làm cho hình mờ của bạn trở nên trong suốt.