---
title: Chỉ định phông chữ mặc định khi kết xuất
linktitle: Chỉ định phông chữ mặc định khi kết xuất
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chỉ định phông chữ mặc định khi hiển thị tài liệu Word bằng Aspose.Words cho .NET. Đảm bảo sự xuất hiện tài liệu nhất quán trên các nền tảng.
type: docs
weight: 10
url: /vi/net/working-with-fonts/specify-default-font-when-rendering/
---
## Giới thiệu

Việc đảm bảo tài liệu Word của bạn hiển thị chính xác trên các nền tảng khác nhau có thể là một thách thức, đặc biệt là khi xử lý khả năng tương thích phông chữ. Một cách để duy trì hình thức nhất quán là chỉ định phông chữ mặc định khi hiển thị tài liệu của bạn sang PDF hoặc các định dạng khác. Trong hướng dẫn này, chúng ta sẽ khám phá cách đặt phông chữ mặc định bằng Aspose.Words cho .NET, để tài liệu của bạn trông đẹp mắt cho dù chúng được xem ở đâu.

## Điều kiện tiên quyết

Trước khi đi sâu vào mã, hãy trình bày những gì bạn cần làm theo cùng với hướng dẫn này:

- Aspose.Words for .NET: Đảm bảo bạn đã cài đặt phiên bản mới nhất. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/words/net/).
- Môi trường phát triển: Visual Studio hoặc bất kỳ môi trường phát triển .NET nào khác.
- Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn cảm thấy thoải mái với lập trình C#.

## Nhập không gian tên

Để bắt đầu, bạn cần nhập các không gian tên cần thiết. Những thứ này sẽ cho phép bạn truy cập các lớp và phương thức cần thiết để làm việc với Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

Bây giờ, hãy chia nhỏ quy trình chỉ định phông chữ mặc định thành các bước dễ thực hiện.

## Bước 1: Thiết lập thư mục tài liệu của bạn

Đầu tiên, xác định đường dẫn đến thư mục tài liệu của bạn. Đây là nơi các tập tin đầu vào và đầu ra của bạn sẽ được lưu trữ.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu của bạn

Tiếp theo, tải tài liệu bạn muốn kết xuất. Trong ví dụ này, chúng tôi sẽ sử dụng tệp có tên "Rendering.docx".

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình cài đặt phông chữ

 Tạo một thể hiện của`FontSettings` và chỉ định phông chữ mặc định. Nếu không tìm thấy phông chữ đã xác định trong quá trình kết xuất, Aspose.Words sẽ sử dụng phông chữ gần nhất có sẵn trên máy.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
```

## Bước 4: Áp dụng cài đặt phông chữ cho tài liệu

Gán cài đặt phông chữ được định cấu hình cho tài liệu của bạn.

```csharp
doc.FontSettings = fontSettings;
```

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu ở định dạng mong muốn. Trong trường hợp này, chúng tôi sẽ lưu nó dưới dạng PDF.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Phần kết luận

Bằng cách làm theo các bước này, bạn có thể đảm bảo rằng tài liệu Word của mình hiển thị với phông chữ mặc định được chỉ định, duy trì tính nhất quán trên các nền tảng khác nhau. Điều này có thể đặc biệt hữu ích đối với các tài liệu được chia sẻ rộng rãi hoặc được xem trên các hệ thống có sẵn phông chữ khác nhau.


## Câu hỏi thường gặp

### Tại sao chỉ định phông chữ mặc định trong Aspose.Words?
Việc chỉ định phông chữ mặc định sẽ đảm bảo tài liệu của bạn xuất hiện nhất quán trên các nền tảng khác nhau, ngay cả khi phông chữ gốc không có sẵn.

### Điều gì xảy ra nếu không tìm thấy phông chữ mặc định trong quá trình kết xuất?
Aspose.Words sẽ sử dụng phông chữ gần nhất có sẵn trên máy để duy trì hình thức của tài liệu giống nhất có thể.

### Tôi có thể chỉ định nhiều phông chữ mặc định không?
 Không, bạn chỉ có thể chỉ định một phông chữ mặc định. Tuy nhiên, bạn có thể xử lý việc thay thế phông chữ cho các trường hợp cụ thể bằng cách sử dụng`FontSettings` lớp học.

### Aspose.Words for .NET có tương thích với tất cả các phiên bản của tài liệu Word không?
Có, Aspose.Words for .NET hỗ trợ nhiều định dạng tài liệu Word, bao gồm DOC, DOCX, RTF, v.v.

### Tôi có thể nhận hỗ trợ ở đâu nếu gặp vấn đề?
 Bạn có thể nhận được hỗ trợ từ cộng đồng Aspose và các nhà phát triển trên[Diễn đàn hỗ trợ Aspose.Words](https://forum.aspose.com/c/words/8).