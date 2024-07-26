---
title: Nhúng phông chữ tập hợp con vào tài liệu PDF
linktitle: Nhúng phông chữ tập hợp con vào tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Giảm kích thước tệp PDF bằng cách chỉ nhúng các tập hợp phông chữ cần thiết bằng Aspose.Words cho .NET. Làm theo hướng dẫn từng bước của chúng tôi để tối ưu hóa tệp PDF của bạn một cách hiệu quả.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/embedded-subset-fonts/
---
## Giới thiệu

Bạn có bao giờ nhận thấy một số tệp PDF lớn hơn nhiều so với các tệp khác, ngay cả khi chúng chứa nội dung tương tự không? Thủ phạm thường nằm ở phông chữ. Nhúng phông chữ vào tệp PDF đảm bảo rằng nó trông giống nhau trên mọi thiết bị, nhưng nó cũng có thể làm tăng kích thước tệp. May mắn thay, Aspose.Words for .NET cung cấp một tính năng tiện dụng để chỉ nhúng các tập hợp phông chữ cần thiết, giữ cho tệp PDF của bạn gọn gàng và hiệu quả. Hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình này, từng bước một.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET: Bạn có thể tải xuống[đây](https://releases.aspose.com/words/net/).
- Môi trường .NET: Đảm bảo bạn có môi trường phát triển .NET đang hoạt động.
- Kiến thức cơ bản về C#: Làm quen với lập trình C# sẽ giúp bạn theo dõi.

## Nhập không gian tên

Để sử dụng Aspose.Words cho .NET, bạn cần nhập các vùng tên cần thiết trong dự án của mình. Thêm những thứ này vào đầu tệp C# của bạn:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Saving;
```

## Bước 1: Tải tài liệu

 Đầu tiên, chúng ta cần tải tài liệu Word mà chúng ta muốn chuyển đổi sang PDF. Việc này được thực hiện bằng cách sử dụng`Document` lớp được cung cấp bởi Aspose.Words.

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

 Đoạn mã này tải tài liệu nằm ở`dataDir` . Đảm bảo thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến tài liệu của bạn.

## Bước 2: Định cấu hình tùy chọn lưu PDF

 Tiếp theo, chúng ta cấu hình`PdfSaveOptions` để đảm bảo rằng chỉ nhúng các tập hợp con phông chữ cần thiết. Bằng cách thiết lập`EmbedFullFonts` ĐẾN`false`, chúng tôi yêu cầu Aspose.Words chỉ nhúng các glyph được sử dụng trong tài liệu.

```csharp
// Tệp PDF đầu ra sẽ chứa các tập hợp con phông chữ trong tài liệu.
// Chỉ các glyph được sử dụng trong tài liệu mới được đưa vào phông chữ PDF.
PdfSaveOptions saveOptions = new PdfSaveOptions { EmbedFullFonts = false };
```

Bước nhỏ nhưng quan trọng này giúp giảm đáng kể kích thước tệp PDF.

## Bước 3: Lưu tài liệu dưới dạng PDF

 Cuối cùng, chúng tôi lưu tài liệu dưới dạng PDF bằng cách sử dụng`Save` phương pháp, áp dụng cấu hình`PdfSaveOptions`.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf", saveOptions);
```

 Mã này sẽ tạo một tệp PDF có tên`WorkingWithPdfSaveOptions.EmbedSubsetFonts.pdf` trong thư mục đã chỉ định, chỉ nhúng các tập hợp phông chữ cần thiết.

## Phần kết luận

Và bạn có nó rồi đấy! Bằng cách làm theo các bước đơn giản này, bạn có thể giảm kích thước tệp PDF của mình một cách hiệu quả bằng cách chỉ nhúng các tập hợp con phông chữ cần thiết bằng Aspose.Words cho .NET. Điều này không chỉ tiết kiệm không gian lưu trữ mà còn đảm bảo thời gian tải nhanh hơn và hiệu suất tốt hơn, đặc biệt đối với các tài liệu có phông chữ phong phú.

## Câu hỏi thường gặp

### Tại sao tôi chỉ nên nhúng các tập hợp phông chữ trong tệp PDF?
Chỉ nhúng các tập hợp phông chữ cần thiết có thể giảm đáng kể kích thước tệp PDF mà không ảnh hưởng đến hình thức và khả năng đọc của tài liệu.

### Tôi có thể quay lại nhúng phông chữ đầy đủ nếu cần không?
 Có, bạn có thể. Đơn giản chỉ cần thiết lập`EmbedFullFonts`tài sản để`true` bên trong`PdfSaveOptions`.

### Aspose.Words for .NET có hỗ trợ các tính năng tối ưu hóa PDF khác không?
Tuyệt đối! Aspose.Words for .NET cung cấp nhiều tùy chọn để tối ưu hóa tệp PDF, bao gồm nén hình ảnh và loại bỏ các đối tượng không sử dụng.

### Những loại phông chữ nào có thể được nhúng tập hợp con bằng Aspose.Words cho .NET?
Aspose.Words for .NET hỗ trợ nhúng tập hợp con cho tất cả các phông chữ TrueType được sử dụng trong tài liệu.

### Làm cách nào tôi có thể xác minh phông chữ nào được nhúng trong tệp PDF của mình?
Bạn có thể mở tệp PDF trong Adobe Acrobat Reader và kiểm tra các thuộc tính trong tab Phông chữ để xem các phông chữ được nhúng.
