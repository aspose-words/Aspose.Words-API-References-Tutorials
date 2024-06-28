---
title: Chèn ảnh nổi vào tài liệu Word
linktitle: Chèn ảnh nổi vào tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn hình ảnh nổi vào tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn từng bước chi tiết này. Hoàn hảo để nâng cao tài liệu của bạn.
type: docs
weight: 10
url: /vi/net/add-content-using-documentbuilder/insert-floating-image/
---
## Giới thiệu

Hãy tưởng tượng việc tạo một báo cáo hoặc đề xuất tuyệt đẹp trong đó hình ảnh được đặt ở vị trí hoàn hảo để bổ sung cho văn bản của bạn. Với Aspose.Words for .NET, bạn có thể đạt được điều này một cách dễ dàng. Thư viện này cung cấp các tính năng mạnh mẽ để thao tác tài liệu, khiến nó trở thành giải pháp phù hợp cho các nhà phát triển. Trong hướng dẫn này, chúng ta sẽ tập trung vào việc chèn một hình ảnh nổi bằng lớp DocumentBuilder. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn từng bước.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào, hãy đảm bảo bạn có mọi thứ bạn cần để bắt đầu:

1.  Aspose.Words for .NET: Bạn có thể tải xuống thư viện từ[Trang phát hành Aspose](https://releases.aspose.com/words/net/).
2. Visual Studio: Bất kỳ phiên bản nào hỗ trợ phát triển .NET.
3. Kiến thức cơ bản về C#: Hiểu những điều cơ bản về lập trình C# sẽ rất hữu ích.
4. Tệp hình ảnh: Tệp hình ảnh bạn muốn chèn, chẳng hạn như logo hoặc hình ảnh.

## Nhập không gian tên

Để sử dụng Aspose.Words trong dự án của bạn, bạn cần nhập các không gian tên cần thiết. Điều này được thực hiện bằng cách thêm các dòng sau vào đầu tệp C# của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Với những điều kiện tiên quyết và không gian tên này, chúng ta đã sẵn sàng bắt đầu phần hướng dẫn của mình.

Hãy chia nhỏ quá trình chèn hình ảnh nổi vào tài liệu Word thành các bước có thể quản lý được. Mỗi bước sẽ được giải thích chi tiết để đảm bảo bạn có thể làm theo mà không gặp bất kỳ trục trặc nào.

## Bước 1: Thiết lập dự án của bạn

Đầu tiên, tạo một dự án C# mới trong Visual Studio. Bạn có thể chọn Ứng dụng Console để đơn giản.

1. Mở Visual Studio và tạo một dự án mới.
2. Chọn "Ứng dụng Console (.NET Core)" và nhấp vào "Tiếp theo".
3. Đặt tên cho dự án của bạn và chọn một vị trí để lưu nó. Nhấp vào "Tạo."
4. Cài đặt Aspose.Words cho .NET thông qua Trình quản lý gói NuGet. Nhấp chuột phải vào dự án của bạn trong Solution Explorer, chọn "Quản lý gói NuGet" và tìm kiếm "Apose.Words". Cài đặt phiên bản mới nhất.

## Bước 2: Khởi tạo Document và DocumentBuilder

Bây giờ dự án của bạn đã được thiết lập, hãy khởi tạo các đối tượng Document và DocumentBuilder.

1.  Tạo một phiên bản mới của`Document` lớp học:

```csharp
Document doc = new Document();
```

2. Khởi tạo một đối tượng DocumentBuilder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Các`Document` đối tượng đại diện cho tài liệu Word và`DocumentBuilder` giúp thêm nội dung vào đó.

## Bước 3: Xác định đường dẫn hình ảnh

Tiếp theo, chỉ định đường dẫn đến tệp hình ảnh của bạn. Đảm bảo hình ảnh của bạn có thể truy cập được từ thư mục dự án của bạn.

Xác định thư mục ảnh và tên file ảnh:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi hình ảnh của bạn được lưu trữ.

## Bước 4: Chèn ảnh nổi

Với mọi thứ đã được thiết lập, hãy chèn hình ảnh nổi vào tài liệu.

 Sử dụng`InsertImage` phương pháp của`DocumentBuilder` lớp để chèn hình ảnh:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

Dưới đây là ý nghĩa của từng tham số:
- `imagePath`Đường dẫn tới file ảnh của bạn.
- `RelativeHorizontalPosition.Margin`: Vị trí nằm ngang so với lề.
- `100`: Độ lệch ngang so với lề (tính bằng điểm).
- `RelativeVerticalPosition.Margin`: Vị trí thẳng đứng so với lề.
- `100`: Độ lệch dọc so với lề (tính bằng điểm).
- `200`: Chiều rộng của hình ảnh (tính bằng điểm).
- `100`: Chiều cao của hình ảnh (tính bằng điểm).
- `WrapType.Square`: Kiểu bao văn bản xung quanh hình ảnh.

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu vào vị trí mong muốn của bạn.

1. Chỉ định đường dẫn tệp đầu ra:

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. Lưu tài liệu:

```csharp
doc.Save(outputPath);
```

Tài liệu Word của bạn với hình ảnh nổi hiện đã sẵn sàng!

## Phần kết luận

Chèn hình ảnh nổi vào tài liệu Word bằng Aspose.Words cho .NET là một quá trình đơn giản khi được chia thành các bước có thể quản lý được. Bằng cách làm theo hướng dẫn này, bạn có thể thêm hình ảnh trông chuyên nghiệp vào tài liệu của mình, nâng cao sức hấp dẫn trực quan của chúng. Aspose.Words cung cấp một API mạnh mẽ giúp thao tác tài liệu trở nên dễ dàng, cho dù bạn đang làm việc trên các báo cáo, đề xuất hay bất kỳ loại tài liệu nào khác.

## Câu hỏi thường gặp

### Tôi có thể chèn nhiều hình ảnh bằng Aspose.Words cho .NET không?

 Có, bạn có thể chèn nhiều hình ảnh bằng cách lặp lại thao tác`InsertImage` phương pháp cho mỗi hình ảnh với các thông số mong muốn.

### Làm cách nào để thay đổi vị trí của hình ảnh?

 Bạn có thể điều chỉnh`RelativeHorizontalPosition`, `RelativeVerticalPosition`và bù các tham số để định vị hình ảnh khi cần thiết.

### Những loại bọc nào khác có sẵn cho hình ảnh?

 Aspose.Words hỗ trợ nhiều loại bọc khác nhau như`Inline`, `TopBottom`, `Tight`, `Through`, và hơn thế nữa. Bạn có thể chọn cái phù hợp nhất với bố cục tài liệu của mình.

### Tôi có thể sử dụng các định dạng hình ảnh khác nhau không?

Có, Aspose.Words hỗ trợ nhiều định dạng hình ảnh bao gồm JPEG, PNG, BMP và GIF.

### Làm cách nào để tôi có được bản dùng thử miễn phí Aspose.Words cho .NET?

 Bạn có thể dùng thử miễn phí từ[Trang dùng thử miễn phí](https://releases.aspose.com/).