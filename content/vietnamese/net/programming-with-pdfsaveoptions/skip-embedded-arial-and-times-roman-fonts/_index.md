---
title: Tối ưu hóa kích thước PDF bằng cách bỏ qua phông chữ Arial & Times Roman được nhúng
linktitle: Tối ưu hóa kích thước PDF bằng cách bỏ qua phông chữ Arial & Times Roman được nhúng
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để tạo tệp PDF được tối ưu hóa mà không cần nhúng phông chữ Arial và Times Roman với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng tính năng này để tối ưu hóa kích thước PDF bằng cách bỏ qua phông chữ Arial và Times Roman được nhúng sang kích thước siêu tệp bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Ở cuối hướng dẫn này, bạn sẽ có thể hiểu cách định cấu hình tùy chọn chế độ nhúng phông chữ trong tài liệu và tạo tệp PDF mà không cần nhúng phông chữ Arial và Times Roman.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu lên

Tiếp theo, chúng ta cần tải tài liệu mà chúng ta muốn xử lý. Trong ví dụ này, chúng tôi giả sử tài liệu có tên là "Rendering.docx" và nằm trong thư mục tài liệu được chỉ định.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu dưới dạng PDF có nhúng phông chữ

 Để bỏ qua việc nhúng phông chữ Arial và Times Roman trong tệp PDF được tạo, chúng ta cần định cấu hình`PdfSaveOptions` đối tượng và thiết lập`FontEmbeddingMode`tài sản để`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Bước 4: Lưu tài liệu dưới dạng PDF không nhúng phông chữ

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng PDF bằng cách sử dụng các tùy chọn lưu đã định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Đó là tất cả ! Bạn đã tạo thành công tệp PDF mà không cần nhúng phông chữ Arial và Times Roman bằng Aspose.Words for .NET.

### Mã nguồn ví dụ để bỏ qua các phông chữ Arial và Times Roman được nhúng ở kích thước siêu tệp với Aspose.Words cho .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách tắt tính năng nhúng phông chữ Arial và Times Roman trong tài liệu PDF bằng Aspose.Words cho .NET. Bằng cách làm theo các bước đã nêu, bạn có thể tạo tệp PDF mà không cần nhúng các phông chữ cụ thể này, điều này có thể giúp giảm kích thước tệp và đảm bảo khả năng tương thích tài liệu tốt hơn trên các nền tảng khác nhau. Hãy chắc chắn xem xét hậu quả của việc tắt tính năng nhúng phông chữ khi sử dụng tính năng này. Vui lòng khám phá thêm các tính năng của Aspose.Words for .NET để tối ưu hóa việc tạo tệp PDF của bạn.

### Các câu hỏi thường gặp

#### Hỏi: Điều gì khiến việc tắt phông chữ Arial và Times Roman nhúng vào tài liệu PDF bị vô hiệu hóa và tại sao điều này lại quan trọng?
Đáp: Vô hiệu hóa việc nhúng phông chữ Arial và Times Roman trong tài liệu PDF là quá trình không đưa các phông chữ này vào tệp PDF được tạo. Điều này có thể quan trọng để giảm kích thước tệp PDF bằng cách tránh bao gồm các phông chữ đã có sẵn phổ biến trên hệ thống đọc PDF. Nó cũng có thể giúp đảm bảo khả năng tương thích tốt hơn và sự xuất hiện nhất quán của tài liệu PDF trên các thiết bị và nền tảng khác nhau.

#### Câu hỏi: Làm cách nào tôi có thể định cấu hình Aspose.Words để .NET không nhúng phông chữ Arial và Times Roman vào tài liệu PDF?
Trả lời: Để định cấu hình Aspose.Words cho .NET không nhúng phông chữ Arial và Times Roman vào tài liệu PDF, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu bạn muốn xử lý bằng cách sử dụng`Document` lớp và đường dẫn tài liệu được chỉ định.

 Tạo một thể hiện của`PdfSaveOptions` lớp và thiết lập`FontEmbeddingMode`tài sản để`PdfFontEmbeddingMode.EmbedAll`. Điều này sẽ nhúng tất cả các phông chữ ngoại trừ Arial và Times Roman vào tệp PDF được tạo.

 Sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu ở định dạng PDF chỉ định các tùy chọn lưu được định cấu hình trước đó.

#### Câu hỏi: Lợi ích của việc tắt tính năng nhúng phông chữ Arial và Times Roman trong tài liệu PDF là gì?
Đáp: Lợi ích của việc tắt tính năng nhúng phông chữ Arial và Times Roman vào tài liệu PDF là:

Giảm kích thước tệp PDF: Bằng cách tránh nhúng các phông chữ phổ biến như Arial và Times Roman, kích thước tệp PDF có thể được giảm, giúp lưu trữ, chia sẻ và truyền tệp dễ dàng hơn.

Khả năng tương thích tốt hơn: Bằng cách sử dụng các phông chữ thường có sẵn trên hệ thống đọc PDF, bạn đảm bảo khả năng tương thích và giao diện tài liệu tốt hơn trên các thiết bị và nền tảng khác nhau.

#### Câu hỏi: Hậu quả của việc tắt tính năng nhúng phông chữ Arial và Times Roman trong tài liệu PDF là gì?
Trả lời: Hậu quả của việc tắt tính năng nhúng phông chữ Arial và Times Roman trong tài liệu PDF như sau:

Hình thức khác: Nếu phông chữ Arial và Times Roman không có sẵn trên hệ thống nơi tệp PDF được mở thì các phông chữ thay thế sẽ được sử dụng, điều này có thể dẫn đến hình thức khác với dự định.

Vấn đề về khả năng đọc: Phông chữ thay thế được sử dụng có thể không dễ đọc như phông chữ gốc, điều này có thể ảnh hưởng đến khả năng đọc của tài liệu.