---
title: Chèn hình dạng
linktitle: Chèn hình dạng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn và thao tác các hình dạng trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước của chúng tôi.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/insert-shape/
---
## Giới thiệu

Khi nói đến việc tạo các tài liệu Word có cấu trúc tốt và hấp dẫn về mặt hình ảnh, hình dạng có thể đóng một vai trò quan trọng. Cho dù bạn đang thêm mũi tên, hộp hay thậm chí là các hình dạng tùy chỉnh phức tạp, khả năng thao tác các thành phần này theo chương trình đều mang lại sự linh hoạt tuyệt vời. Trong hướng dẫn này, chúng ta sẽ khám phá cách chèn và thao tác các hình dạng trong tài liệu Word bằng Aspose.Words cho .NET.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

1.  Aspose.Words for .NET: Tải xuống và cài đặt phiên bản mới nhất từ[Trang phát hành Aspose](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Môi trường phát triển .NET phù hợp như Visual Studio.
3. Kiến thức cơ bản về C#: Làm quen với ngôn ngữ lập trình C# và các khái niệm cơ bản.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các vùng tên cần thiết trong dự án C# của mình:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Bước 1: Thiết lập dự án của bạn

Trước khi có thể bắt đầu chèn hình, bạn cần thiết lập dự án của mình và thêm thư viện Aspose.Words cho .NET.

1. Tạo một dự án mới: Mở Visual Studio và tạo dự án Ứng dụng bảng điều khiển C# mới.
2. Thêm Aspose.Words cho .NET: Cài đặt thư viện Aspose.Words cho .NET thông qua Trình quản lý gói NuGet.

```bash
Install-Package Aspose.Words
```

## Bước 2: Khởi tạo tài liệu

Trước tiên, bạn sẽ cần khởi tạo một tài liệu mới và một trình tạo tài liệu, điều này sẽ giúp xây dựng tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Khởi tạo một tài liệu mới
Document doc = new Document();

// Khởi tạo DocumentBuilder để giúp xây dựng tài liệu
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn hình dạng

Bây giờ, hãy chèn một hình vào tài liệu. Chúng ta sẽ bắt đầu bằng cách thêm một hộp văn bản đơn giản.

```csharp
// Chèn hình dạng hộp văn bản vào tài liệu
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100, RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// Xoay hình dạng
shape.Rotation = 30.0;
```

Trong ví dụ này, chúng tôi chèn một hộp văn bản ở vị trí (100, 100) với chiều rộng và chiều cao là 50 đơn vị mỗi hộp. Chúng ta cũng xoay hình này 30 độ.

## Bước 4: Thêm hình dạng khác

Hãy thêm một hình dạng khác vào tài liệu, lần này không chỉ định vị trí.

```csharp
// Thêm một hình dạng hộp văn bản khác
Shape secondShape = builder.InsertShape(ShapeType.TextBox, 50, 50);

// Xoay hình dạng
secondShape.Rotation = 30.0;
```

Đoạn mã này chèn một hộp văn bản khác có cùng kích thước và góc xoay như hộp đầu tiên nhưng không chỉ định vị trí của nó.

## Bước 5: Lưu tài liệu

 Sau khi thêm hình dạng, bước cuối cùng là lưu tài liệu. Chúng tôi sẽ sử dụng`OoxmlSaveOptions` để chỉ định định dạng lưu.

```csharp
// Xác định các tùy chọn lưu tuân thủ
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};

// Lưu tài liệu
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Phần kết luận

Và bạn có nó! Bạn đã chèn và thao tác thành công các hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn này bao gồm những điều cơ bản, nhưng Aspose.Words cung cấp nhiều tính năng nâng cao hơn để làm việc với các hình dạng, chẳng hạn như kiểu tùy chỉnh, trình kết nối và hình dạng nhóm.

 Để biết thêm thông tin chi tiết, hãy truy cập[Aspose.Words cho tài liệu .NET](https://reference.aspose.com/words/net/).

## Câu hỏi thường gặp

### Làm cách nào để chèn các loại hình dạng khác nhau?
Bạn có thể thay đổi`ShapeType` trong`InsertShape` phương pháp chèn các loại hình dạng khác nhau như hình tròn, hình chữ nhật và mũi tên.

### Tôi có thể thêm văn bản bên trong các hình dạng không?
 Có, bạn có thể sử dụng`builder.Write` phương pháp thêm văn bản bên trong các hình sau khi chèn chúng.

### Có thể tạo kiểu cho các hình dạng không?
 Có, bạn có thể tạo kiểu cho các hình dạng bằng cách đặt các thuộc tính như`FillColor`, `StrokeColor` , Và`StrokeWeight`.

### Làm cách nào để định vị hình dạng so với các phần tử khác?
 Sử dụng`RelativeHorizontalPosition`Và`RelativeVerticalPosition` các thuộc tính để định vị hình dạng so với các phần tử khác trong tài liệu.

### Tôi có thể nhóm nhiều hình dạng lại với nhau không?
 Có, Aspose.Words for .NET cho phép bạn nhóm các hình dạng bằng cách sử dụng`GroupShape` lớp học.