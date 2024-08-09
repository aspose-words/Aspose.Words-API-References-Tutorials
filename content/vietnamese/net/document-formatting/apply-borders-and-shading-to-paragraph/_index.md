---
title: Áp dụng viền và tô bóng cho đoạn văn trong tài liệu Word
linktitle: Áp dụng viền và tô bóng cho đoạn văn trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Áp dụng đường viền và bóng cho các đoạn văn trong tài liệu Word bằng Aspose.Words for .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để cải thiện định dạng tài liệu của bạn.
type: docs
weight: 10
url: /vi/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## Giới thiệu

Xin chào, bạn đã bao giờ tự hỏi làm cách nào để làm cho tài liệu Word của mình nổi bật với một số đường viền và bóng đẹp mắt chưa? Vâng, bạn đang ở đúng nơi! Hôm nay, chúng ta sẽ đi sâu vào thế giới của Aspose.Words dành cho .NET để làm nổi bật các đoạn văn của chúng ta. Hãy tưởng tượng tài liệu của bạn trông bóng bẩy như tác phẩm của một nhà thiết kế chuyên nghiệp chỉ với một vài dòng mã. Sẵn sàng để bắt đầu? Đi thôi!

## Điều kiện tiên quyết

Trước khi xắn tay áo và lao vào viết mã, hãy đảm bảo rằng chúng ta có mọi thứ mình cần. Đây là danh sách kiểm tra nhanh của bạn:

-  Aspose.Words for .NET: Bạn cần cài đặt thư viện này. Bạn có thể tải nó xuống từ[trang web giả định](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ IDE nào khác hỗ trợ .NET.
- Kiến thức cơ bản về C#: Chỉ đủ để hiểu và chỉnh sửa các đoạn mã.
- Giấy phép hợp lệ: Hoặc là[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) hoặc một cái được mua từ[giả định](https://purchase.aspose.com/buy).

## Nhập không gian tên

Trước khi bắt đầu viết mã, chúng ta cần đảm bảo rằng chúng ta đã nhập các không gian tên cần thiết vào dự án của mình. Điều này làm cho tất cả các tính năng thú vị của Aspose.Words có thể truy cập được đối với chúng tôi.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

Bây giờ, hãy chia quy trình thành các bước nhỏ. Mỗi bước sẽ có tiêu đề và giải thích chi tiết. Sẵn sàng? Đi thôi!

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước tiên, chúng ta cần một nơi để lưu tài liệu được định dạng đẹp mắt của mình. Hãy đặt đường dẫn đến thư mục tài liệu của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Thư mục này là nơi tài liệu cuối cùng của bạn sẽ được lưu. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế trên máy của bạn.

## Bước 2: Tạo Tài liệu mới và DocumentBuilder

 Tiếp theo, chúng ta cần tạo một tài liệu mới và một`DocumentBuilder` sự vật. các`DocumentBuilder` là cây đũa thần cho phép chúng ta thao tác với tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 các`Document` đối tượng đại diện cho toàn bộ tài liệu Word của chúng tôi và`DocumentBuilder` giúp chúng tôi thêm và định dạng nội dung.

## Bước 3: Xác định đường viền đoạn văn

Bây giờ, hãy thêm một số đường viền phong cách vào đoạn văn của chúng ta. Chúng tôi sẽ xác định khoảng cách từ văn bản và đặt các kiểu đường viền khác nhau.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

Ở đây, chúng tôi đặt khoảng cách 20 điểm giữa văn bản và đường viền. Các đường viền ở tất cả các bên (trái, phải, trên, dưới) được đặt thành đường đôi. Lạ mắt phải không?

## Bước 4: Áp dụng tô bóng cho đoạn văn

Đường viền rất tuyệt, nhưng chúng ta hãy nâng nó lên một chút bằng cách tạo bóng. Chúng ta sẽ sử dụng mẫu chéo chéo với sự pha trộn màu sắc để làm nổi bật đoạn văn của chúng ta.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

Trong bước này, chúng tôi áp dụng kết cấu chéo chéo với san hô nhạt làm màu nền và cá hồi nhạt làm màu nền trước. Nó giống như mặc cho đoạn văn của bạn những bộ quần áo hàng hiệu!

## Bước 5: Thêm văn bản vào đoạn văn

Đoạn văn không có văn bản là gì? Hãy thêm một câu mẫu để xem cách định dạng của chúng tôi hoạt động như thế nào.

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

Dòng này chèn văn bản của chúng tôi vào tài liệu. Đơn giản nhưng giờ đây nó được bao bọc trong một khung hình đầy phong cách và nền bóng mờ.

## Bước 6: Lưu tài liệu

Cuối cùng, đã đến lúc lưu lại công việc của chúng ta. Hãy lưu tài liệu vào thư mục đã chỉ định với tên mô tả.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 Điều này lưu tài liệu của chúng tôi với tên`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` trong thư mục chúng tôi đã chỉ định trước đó.

## Phần kết luận

Và bạn có nó! Chỉ với một vài dòng mã, chúng tôi đã biến một đoạn văn đơn giản thành một đoạn nội dung hấp dẫn về mặt hình ảnh. Aspose.Words for .NET giúp việc thêm định dạng trông chuyên nghiệp vào tài liệu của bạn trở nên vô cùng dễ dàng. Cho dù bạn đang chuẩn bị một báo cáo, một lá thư hay bất kỳ tài liệu nào, những thủ thuật này sẽ giúp bạn tạo ấn tượng tuyệt vời. Vì vậy, hãy tiếp tục, dùng thử và xem tài liệu của bạn trở nên sống động!

## Câu hỏi thường gặp

### Tôi có thể sử dụng các kiểu đường khác nhau cho mỗi đường viền không?  
 Tuyệt đối! Aspose.Words for .NET cho phép bạn tùy chỉnh từng đường viền riêng lẻ. Chỉ cần thiết lập`LineStyle` cho từng loại đường viền như trong hướng dẫn.

### Những kết cấu bóng khác có sẵn?  
 Có một số họa tiết bạn có thể sử dụng, chẳng hạn như sọc liền, sọc ngang, sọc dọc, v.v. Kiểm tra[Cung cấp tài liệu](https://reference.aspose.com/words/net/) để có danh sách đầy đủ.

### Làm cách nào để thay đổi màu đường viền?  
 Bạn có thể đặt màu đường viền bằng cách sử dụng`Color` tài sản cho mỗi biên giới. Ví dụ,`borders[BorderType.Left].Color = Color.Red;`.

### Có thể áp dụng đường viền và tô bóng cho một phần cụ thể của văn bản không?  
 Có, bạn có thể áp dụng đường viền và tô bóng cho các dòng văn bản cụ thể bằng cách sử dụng`Run` đối tượng bên trong`DocumentBuilder`.

### Tôi có thể tự động hóa quá trình này cho nhiều đoạn văn không?  
Chắc chắn! Bạn có thể lặp qua các đoạn văn của mình và áp dụng các cài đặt đường viền và bóng tương tự theo chương trình.
