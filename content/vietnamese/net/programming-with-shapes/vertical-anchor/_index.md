---
title: Neo dọc
linktitle: Neo dọc
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt vị trí neo dọc cho hộp văn bản trong tài liệu Word bằng Aspose.Words cho .NET. Bao gồm hướng dẫn từng bước dễ dàng.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/vertical-anchor/
---
## Giới thiệu

Bạn đã bao giờ thấy mình cần kiểm soát chính xác vị trí văn bản xuất hiện bên trong hộp văn bản trong tài liệu Word chưa? Có thể bạn muốn văn bản của mình được neo vào đầu, giữa hoặc cuối hộp văn bản? Nếu vậy, bạn đang ở đúng nơi! Trong hướng dẫn này, chúng ta sẽ khám phá cách sử dụng Aspose.Words cho .NET để đặt neo dọc của hộp văn bản trong tài liệu Word. Hãy nghĩ về việc neo dọc như cây đũa thần giúp định vị văn bản của bạn một cách chính xác ở nơi bạn muốn trong vùng chứa nó. Sẵn sàng để đi sâu vào? Bắt đầu nào!

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào các vấn đề cơ bản về neo dọc, bạn sẽ cần chuẩn bị sẵn một số thứ:

1.  Aspose.Words for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words for .NET. Nếu bạn chưa có nó, bạn có thể[tải về tại đây](https://releases.aspose.com/words/net/).
2. Visual Studio: Hướng dẫn này giả sử bạn đang sử dụng Visual Studio hoặc .NET IDE khác để mã hóa.
3. Kiến thức cơ bản về C#: Làm quen với C# và .NET sẽ giúp bạn theo dõi suôn sẻ.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các vùng tên cần thiết vào mã C# của mình. Đây là nơi bạn cho ứng dụng biết nơi tìm các lớp và phương thức bạn sẽ sử dụng. Đây là cách thực hiện:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Các không gian tên này cung cấp các lớp bạn sẽ cần để làm việc với tài liệu và hình dạng.

## Bước 1: Khởi tạo tài liệu

Trước tiên, bạn cần tạo một tài liệu Word mới. Hãy coi điều này giống như việc thiết lập khung vẽ của bạn trước khi bắt đầu vẽ.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Đây,`Document` là khung vẽ trống của bạn và`DocumentBuilder` là cọ vẽ của bạn, cho phép bạn thêm hình dạng và văn bản.

## Bước 2: Chèn hình dạng hộp văn bản

Bây giờ, hãy thêm một hộp văn bản vào tài liệu của chúng ta. Đây là nơi văn bản của bạn sẽ sống. 

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

 Trong ví dụ này,`ShapeType.TextBox` chỉ định hình dạng bạn muốn và`200, 200` là chiều rộng và chiều cao của hộp văn bản tính bằng điểm.

## Bước 3: Đặt neo dọc

Đây là nơi phép thuật xảy ra! Bạn có thể đặt căn chỉnh theo chiều dọc của văn bản trong hộp văn bản. Điều này xác định xem văn bản được neo vào đầu, giữa hay cuối hộp văn bản.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

 Trong trường hợp này,`TextBoxAnchor.Bottom`đảm bảo rằng văn bản sẽ được neo vào cuối hộp văn bản. Nếu bạn muốn nó ở giữa hoặc căn chỉnh lên trên cùng, bạn sẽ sử dụng`TextBoxAnchor.Center` hoặc`TextBoxAnchor.Top`, tương ứng.

## Bước 4: Thêm văn bản vào TextBox

Bây giờ là lúc thêm một số nội dung vào hộp văn bản của bạn. Hãy nghĩ về nó như việc điền vào khung vẽ của bạn với những nét hoàn thiện cuối cùng.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

 Đây,`MoveTo` đảm bảo rằng văn bản được chèn vào hộp văn bản và`Write` thêm văn bản thực tế.

## Bước 5: Lưu tài liệu

Bước cuối cùng là lưu tài liệu của bạn. Điều này giống như việc bạn đặt bức tranh đã hoàn thành của mình vào khung.

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

## Phần kết luận

Và bạn có nó rồi đấy! Bạn vừa học cách kiểm soát việc căn chỉnh văn bản theo chiều dọc trong hộp văn bản trong tài liệu Word bằng Aspose.Words for .NET. Cho dù bạn đang neo văn bản vào đầu, giữa hay dưới cùng, tính năng này sẽ mang lại cho bạn quyền kiểm soát chính xác bố cục tài liệu của mình. Vì vậy, lần tới khi bạn cần điều chỉnh vị trí văn bản trong tài liệu của mình, bạn sẽ biết phải làm gì!

## Câu hỏi thường gặp

### Neo dọc trong tài liệu Word là gì?
Các điều khiển neo dọc trong đó văn bản được định vị trong hộp văn bản, chẳng hạn như căn chỉnh trên cùng, giữa hoặc dưới cùng.

### Tôi có thể sử dụng các hình dạng khác ngoài hộp văn bản không?
Có, bạn có thể sử dụng tính năng neo dọc với các hình dạng khác, mặc dù hộp văn bản là trường hợp sử dụng phổ biến nhất.

### Làm cách nào để thay đổi điểm neo sau khi tạo hộp văn bản?
 Bạn có thể thay đổi điểm neo bằng cách đặt`VerticalAnchor` thuộc tính trên đối tượng hình dạng hộp văn bản.

### Có thể neo văn bản vào giữa hộp văn bản không?
 Tuyệt đối! Chỉ dùng`TextBoxAnchor.Center` để căn giữa văn bản theo chiều dọc trong hộp văn bản.

### Tôi có thể tìm thêm thông tin về Aspose.Words cho .NET ở đâu?
 Kiểm tra[Tài liệu Aspose.Words](https://reference.aspose.com/words/net/) để biết thêm chi tiết và hướng dẫn.