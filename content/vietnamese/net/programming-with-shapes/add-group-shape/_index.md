---
title: Thêm hình dạng nhóm
linktitle: Thêm hình dạng nhóm
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm hình dạng nhóm vào tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước toàn diện này.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/add-group-shape/
---
## Giới thiệu

Tạo các tài liệu phức tạp với các yếu tố hình ảnh phong phú đôi khi có thể là một nhiệm vụ khó khăn, đặc biệt là khi xử lý các hình dạng nhóm. Nhưng đừng sợ! Aspose.Words for .NET đơn giản hóa quá trình này, khiến nó trở nên dễ dàng như ăn bánh. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để thêm các hình dạng nhóm vào tài liệu Word của bạn. Sẵn sàng để đi sâu vào? Hãy bắt đầu!

## Điều kiện tiên quyết

Trước khi chúng tôi bắt đầu, hãy đảm bảo bạn có những điều sau:

1.  Aspose.Words for .NET: Bạn có thể tải xuống từ[Trang phát hành Aspose](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ IDE nào khác tương thích với .NET.
3. Hiểu biết cơ bản về C#: Làm quen với lập trình C# là một lợi thế.

## Nhập không gian tên

Để bắt đầu, chúng ta cần nhập các không gian tên cần thiết trong dự án của mình. Các không gian tên này cung cấp quyền truy cập vào các lớp và phương thức cần thiết để thao tác với tài liệu Word bằng Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Bước 1: Khởi tạo tài liệu

Trước tiên, hãy khởi tạo một tài liệu Word mới. Hãy coi điều này giống như việc tạo một khung vẽ trống nơi chúng ta sẽ thêm các hình dạng nhóm của mình.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Đây,`EnsureMinimum()` thêm một tập hợp nút tối thiểu cần thiết cho tài liệu.

## Bước 2: Tạo đối tượng GroupShape

 Tiếp theo, chúng ta cần tạo một`GroupShape`sự vật. Đối tượng này sẽ đóng vai trò là nơi chứa các hình dạng khác, cho phép chúng ta nhóm chúng lại với nhau.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Bước 3: Thêm hình vào GroupShape

 Bây giờ, hãy thêm các hình dạng riêng lẻ vào`GroupShape` thùng chứa. Chúng ta sẽ bắt đầu với hình dạng đường viền có điểm nhấn và sau đó thêm hình dạng nút hành động.

### Thêm hình dạng đường viền có dấu

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Đoạn mã này tạo một hình dạng đường viền có dấu với chiều rộng và chiều cao là 100 đơn vị và thêm nó vào`GroupShape`.

### Thêm hình dạng nút hành động

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Ở đây, chúng ta tạo một hình dạng nút hành động, định vị nó và thêm nó vào`GroupShape`.

## Bước 4: Xác định kích thước GroupShape

 Để đảm bảo các hình dạng của chúng ta vừa khít trong nhóm, chúng ta cần đặt kích thước của`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Điều này xác định chiều rộng và chiều cao của`GroupShape` là 200 đơn vị và đặt kích thước tọa độ tương ứng.

## Bước 5: Chèn GroupShape vào Tài liệu

 Bây giờ, hãy chèn`GroupShape` vào tài liệu bằng cách sử dụng`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` cung cấp một cách dễ dàng để thêm các nút, bao gồm cả hình dạng, vào tài liệu.

## Bước 6: Lưu tài liệu

Cuối cùng, lưu tài liệu vào thư mục được chỉ định của bạn.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Và bạn có nó! Tài liệu của bạn với các hình nhóm đã sẵn sàng.

## Phần kết luận

Việc thêm các hình dạng nhóm vào tài liệu Word của bạn không phải là một quá trình phức tạp. Với Aspose.Words cho .NET, bạn có thể tạo và thao tác các hình dạng một cách dễ dàng, làm cho tài liệu của bạn trở nên hấp dẫn và hữu dụng hơn về mặt trực quan. Hãy làm theo các bước được nêu trong hướng dẫn này và bạn sẽ trở thành chuyên gia ngay lập tức!

## Câu hỏi thường gặp

### Tôi có thể thêm nhiều hơn hai hình vào một GroupShape không?
 Có, bạn có thể thêm bao nhiêu hình dạng tùy thích vào một`GroupShape` . Chỉ cần sử dụng`AppendChild` phương pháp cho từng hình.

### Có thể tạo kiểu cho các hình dạng trong GroupShape không?
 Tuyệt đối! Mỗi hình dạng có thể được tạo kiểu riêng bằng cách sử dụng các thuộc tính có sẵn trong`Shape` lớp học.

### Làm cách nào để định vị GroupShape trong tài liệu?
 Bạn có thể định vị`GroupShape` bằng cách thiết lập nó`Left`Và`Top` của cải.

### Tôi có thể thêm văn bản vào các hình trong GroupShape không?
 Có, bạn có thể thêm văn bản vào hình bằng cách sử dụng`AppendChild` phương pháp để thêm một`Paragraph` chứa đựng`Run` các nút có văn bản.

### Có thể nhóm các hình dạng động dựa trên đầu vào của người dùng không?
Có, bạn có thể tự động tạo và nhóm các hình dạng dựa trên thông tin đầu vào của người dùng bằng cách điều chỉnh các thuộc tính và phương thức tương ứng.