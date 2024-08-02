---
title: Bố cục trong ô
linktitle: Bố cục trong ô
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt bố cục trong ô bằng Aspose.Words cho .NET với hướng dẫn toàn diện này. Hoàn hảo cho các nhà phát triển muốn tùy chỉnh tài liệu Word.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/layout-in-cell/
---
## Giới thiệu

Nếu bạn từng muốn tinh chỉnh bố cục các ô bảng trong tài liệu Word theo chương trình thì bạn đã đến đúng nơi. Hôm nay, chúng ta sẽ đi sâu vào cách thiết lập bố cục trong ô bằng Aspose.Words cho .NET. Chúng ta sẽ xem qua một ví dụ thực tế, chia nhỏ từng bước để bạn có thể dễ dàng làm theo.

## Điều kiện tiên quyết

Trước khi chúng ta chuyển sang mã, hãy đảm bảo bạn có mọi thứ mình cần:

1.  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words for .NET. Nếu chưa, bạn có thể[tải về tại đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Bạn sẽ cần thiết lập môi trường phát triển với .NET. Visual Studio là một lựa chọn tuyệt vời nếu bạn đang tìm kiếm đề xuất.
3. Kiến thức cơ bản về C#: Mặc dù tôi sẽ giải thích từng bước nhưng hiểu biết cơ bản về C# sẽ giúp bạn thực hiện dễ dàng hơn.
4.  Thư mục Tài liệu: Chuẩn bị đường dẫn thư mục nơi bạn sẽ lưu tài liệu của mình. Chúng ta sẽ gọi điều này là`YOUR DOCUMENT DIRECTORY`.

## Nhập không gian tên

Để bắt đầu, hãy đảm bảo bạn đang nhập các không gian tên cần thiết trong dự án của mình:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Hãy chia nhỏ quy trình thành các bước có thể quản lý được.

## Bước 1: Tạo một tài liệu mới

 Đầu tiên, chúng ta sẽ tạo một tài liệu Word mới và khởi tạo một`DocumentBuilder` đối tượng để giúp chúng tôi xây dựng nội dung của chúng tôi.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Bắt đầu một bảng và đặt định dạng hàng

Chúng ta sẽ bắt đầu xây dựng một bảng và chỉ định quy tắc về chiều cao và chiều cao cho các hàng.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Bước 3: Chèn ô và điền nội dung

Tiếp theo, chúng ta lặp để chèn ô vào bảng. Cứ 7 ô, chúng ta sẽ kết thúc hàng để tạo một ô mới.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Bước 4: Thêm hình mờ

 Bây giờ, hãy thêm hình mờ vào tài liệu của chúng ta. Chúng ta sẽ tạo một`Shape` đối tượng và thiết lập các thuộc tính của nó.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Hiển thị hình dạng bên ngoài ô của bảng nếu nó sẽ được đặt vào một ô.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Bước 5: Tùy chỉnh giao diện hình mờ

Chúng tôi sẽ tùy chỉnh thêm giao diện của hình mờ bằng cách đặt thuộc tính màu sắc và văn bản của hình mờ.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Bước 6: Chèn Watermark vào tài liệu

Chúng ta sẽ tìm lần chạy cuối cùng trong tài liệu và chèn hình mờ vào vị trí đó.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Bước 7: Tối ưu hóa tài liệu cho Word 2010

Để đảm bảo tính tương thích, chúng tôi sẽ tối ưu hóa tài liệu cho Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Bước 8: Lưu tài liệu

Cuối cùng, chúng ta sẽ lưu tài liệu của mình vào thư mục đã chỉ định.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Phần kết luận

Và bạn có nó rồi đấy! Bạn đã tạo thành công tài liệu Word với bố cục bảng tùy chỉnh và thêm hình mờ bằng Aspose.Words cho .NET. Hướng dẫn này nhằm mục đích cung cấp hướng dẫn rõ ràng, từng bước để giúp bạn hiểu từng phần của quy trình. Với những kỹ năng này, giờ đây bạn có thể tạo các tài liệu Word phức tạp và tùy chỉnh hơn theo chương trình.

## Câu hỏi thường gặp

### Tôi có thể sử dụng phông chữ khác cho văn bản hình mờ không?
 Có, bạn có thể thay đổi phông chữ bằng cách đặt`watermark.TextPath.FontFamily` thuộc tính cho phông chữ bạn muốn.

### Làm cách nào để điều chỉnh vị trí của hình mờ?
 Bạn có thể sửa đổi`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , Và`VerticalAlignment` các thuộc tính để điều chỉnh vị trí của hình mờ.

### Có thể sử dụng hình ảnh thay vì văn bản cho hình mờ không?
 Tuyệt đối! Bạn có thể tạo một`Shape` với loại`ShapeType.Image` và thiết lập hình ảnh của nó bằng cách sử dụng`ImageData.SetImage` phương pháp.

### Tôi có thể tạo các bảng có chiều cao hàng khác nhau không?
Có, bạn có thể đặt độ cao khác nhau cho mỗi hàng bằng cách thay đổi`RowFormat.Height` thuộc tính trước khi chèn ô vào hàng đó.

### Làm cách nào để xóa hình mờ khỏi tài liệu?
 Bạn có thể xóa hình mờ bằng cách định vị nó trong bộ sưu tập hình dạng của tài liệu và gọi phương thức`Remove` phương pháp.