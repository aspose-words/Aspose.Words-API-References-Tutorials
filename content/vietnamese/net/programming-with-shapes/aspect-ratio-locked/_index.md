---
title: Tỷ lệ khung hình đã bị khóa
linktitle: Tỷ lệ khung hình đã bị khóa
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách khóa tỷ lệ khung hình của hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Hãy làm theo hướng dẫn từng bước này để giữ cho hình ảnh và hình dạng của bạn cân đối.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/aspect-ratio-locked/
---
## Giới thiệu

Bạn đã bao giờ tự hỏi làm cách nào để duy trì tỷ lệ hình ảnh và hình dạng hoàn hảo trong tài liệu Word của mình chưa? Đôi khi, bạn cần đảm bảo rằng hình ảnh và hình dạng của mình không bị biến dạng khi thay đổi kích thước. Đây là lúc việc khóa tỷ lệ khung hình trở nên hữu ích. Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt tỷ lệ khung hình cho hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ chia nó thành các bước dễ thực hiện để đảm bảo bạn có thể tự tin áp dụng những kỹ năng này vào dự án của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy xem qua những gì bạn cần để bắt đầu:

- Thư viện Aspose.Words for .NET: Bạn cần cài đặt Aspose.Words for .NET. Nếu bạn chưa có, bạn có thể[tải về tại đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET. Visual Studio là một lựa chọn phổ biến.
- Kiến thức cơ bản về C#: Một số kiến thức quen thuộc về lập trình C# sẽ rất hữu ích.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Những không gian tên này sẽ cung cấp cho chúng ta quyền truy cập vào các lớp và phương thức mà chúng ta cần để làm việc với các tài liệu và hình dạng Word.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

 Trước khi bắt đầu thao tác với các hình dạng, chúng ta cần thiết lập một thư mục nơi tài liệu của chúng ta sẽ được lưu trữ. Để đơn giản, chúng ta sẽ sử dụng phần giữ chỗ`YOUR DOCUMENT DIRECTORY`. Thay thế đường dẫn này bằng đường dẫn thực tế tới thư mục tài liệu của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo một tài liệu mới

Tiếp theo, chúng ta sẽ tạo một tài liệu Word mới bằng Aspose.Words. Tài liệu này sẽ đóng vai trò là khung vẽ của chúng tôi để thêm hình dạng và hình ảnh.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Ở đây, chúng ta tạo một thể hiện của`Document` lớp và sử dụng một`DocumentBuilder` để giúp chúng tôi xây dựng nội dung tài liệu.

## Bước 3: Chèn hình ảnh

 Bây giờ, hãy chèn một hình ảnh vào tài liệu của chúng ta. Chúng tôi sẽ sử dụng`InsertImage` phương pháp của`DocumentBuilder`lớp học. Đảm bảo bạn có hình ảnh trong thư mục được chỉ định.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Thay thế`dataDir + "Transparent background logo.png"` với đường dẫn đến tập tin hình ảnh của bạn.

## Bước 4: Khóa tỷ lệ khung hình

Sau khi hình ảnh được chèn, chúng ta có thể khóa tỷ lệ khung hình của nó. Khóa tỷ lệ khung hình đảm bảo tỷ lệ của hình ảnh không đổi khi thay đổi kích thước.

```csharp
shape.AspectRatioLocked = true;
```

 Cài đặt`AspectRatioLocked` ĐẾN`true` đảm bảo rằng hình ảnh duy trì tỷ lệ khung hình ban đầu.

## Bước 5: Lưu tài liệu

Cuối cùng, chúng ta sẽ lưu tài liệu vào thư mục đã chỉ định. Bước này ghi tất cả những thay đổi mà chúng tôi đã thực hiện vào tệp tài liệu.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách đặt tỷ lệ khung hình cho hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước này, bạn có thể đảm bảo rằng hình ảnh và hình dạng của bạn giữ nguyên tỷ lệ, làm cho tài liệu của bạn trông chuyên nghiệp và bóng bẩy. Hãy thoải mái thử nghiệm với các hình ảnh và hình dạng khác nhau để xem tính năng khóa tỷ lệ khung hình hoạt động như thế nào trong các tình huống khác nhau.

## Câu hỏi thường gặp

### Tôi có thể mở khóa tỷ lệ khung hình sau khi khóa không?
Có, bạn có thể mở khóa tỷ lệ khung hình bằng cách cài đặt`shape.AspectRatioLocked = false`.

### Điều gì xảy ra nếu tôi thay đổi kích thước hình ảnh có tỷ lệ khung hình bị khóa?
Hình ảnh sẽ thay đổi kích thước theo tỷ lệ, duy trì tỷ lệ chiều rộng và chiều cao ban đầu.

### Tôi có thể áp dụng điều này cho các hình dạng khác ngoài hình ảnh không?
Tuyệt đối! Tính năng khóa tỷ lệ khung hình có thể được áp dụng cho bất kỳ hình dạng nào, bao gồm hình chữ nhật, hình tròn, v.v.

### Aspose.Words cho .NET có tương thích với .NET Core không?
Có, Aspose.Words for .NET hỗ trợ cả .NET Framework và .NET Core.

### Tôi có thể tìm thêm tài liệu về Aspose.Words cho .NET ở đâu?
 Bạn có thể tìm thấy tài liệu toàn diện[đây](https://reference.aspose.com/words/net/).