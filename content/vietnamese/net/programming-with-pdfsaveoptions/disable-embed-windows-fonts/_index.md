---
title: Giảm kích thước PDF bằng cách tắt phông chữ nhúng
linktitle: Giảm kích thước PDF bằng cách tắt phông chữ nhúng
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách giảm kích thước PDF bằng cách tắt tính năng nhúng phông chữ của Windows khi chuyển đổi tài liệu sang PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để giảm kích thước PDF bằng cách tắt tính năng nhúng phông chữ Windows vào tài liệu PDF bằng Aspose.Words cho .NET. Bằng cách tắt tính năng nhúng phông chữ, bạn có thể giảm kích thước tệp PDF được tạo. Làm theo các bước dưới đây:

## Bước 1: Tải tài liệu

Bắt đầu bằng cách tải lên tài liệu bạn muốn chuyển đổi sang PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Hãy chắc chắn chỉ định đường dẫn chính xác đến tài liệu của bạn.

## Bước 2: Đặt tùy chọn lưu PDF

Tạo một phiên bản của lớp PdfSaveOptions và chỉ định cách nhúng phông chữ:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Tùy chọn này cho phép bạn hủy kích hoạt tính năng tích hợp phông chữ Windows trong tệp PDF được tạo.

## Bước 3: Chuyển đổi tài liệu sang PDF

 Sử dụng`Save` phương pháp chuyển đổi tài liệu sang PDF chỉ định các tùy chọn chuyển đổi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Đảm bảo chỉ định đường dẫn chính xác để lưu tệp PDF đã chuyển đổi.

### Mã nguồn ví dụ cho Tắt phông chữ nhúng Windows bằng Aspose.Words cho .NET

Đây là mã nguồn đầy đủ để tắt tính năng nhúng phông chữ Windows vào tài liệu PDF bằng Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Tệp PDF đầu ra sẽ được lưu mà không cần nhúng phông chữ Windows tiêu chuẩn.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Bằng cách làm theo các bước này, bạn có thể dễ dàng vô hiệu hóa tính năng nhúng phông chữ Windows vào tài liệu PDF bằng Aspose.Words cho .NET.


## Phần kết luận

Trong hướng dẫn này, chúng tôi đã tìm hiểu cách giảm kích thước tệp PDF bằng cách tắt tính năng nhúng phông chữ Windows bằng Aspose.Words cho .NET. Bằng cách tắt tính năng nhúng phông chữ, bạn có thể giảm kích thước tệp PDF được tạo, giúp lưu trữ, chia sẻ và truyền tệp dễ dàng hơn. Tuy nhiên, điều quan trọng cần lưu ý là việc tắt tính năng nhúng phông chữ của Windows có thể gây ra những thay đổi về hình thức và định dạng trong tài liệu PDF cuối cùng. Hãy chắc chắn xem xét những hậu quả này khi sử dụng tính năng này. Vui lòng khám phá thêm các tính năng của Aspose.Words for .NET để tối ưu hóa việc tạo tệp PDF của bạn.

### Các câu hỏi thường gặp

#### Hỏi: Điều gì khiến việc tắt tính năng nhúng phông chữ Windows vào tài liệu PDF bị vô hiệu hóa và tại sao điều này lại quan trọng?
Trả lời: Vô hiệu hóa tính năng nhúng phông chữ Windows vào tài liệu PDF là quá trình ngăn không cho phông chữ Windows được đưa vào tệp PDF được tạo. Điều này làm giảm kích thước tệp PDF bằng cách xóa dữ liệu phông chữ Windows được nhúng. Điều này có thể quan trọng để giảm kích thước tệp PDF, giúp lưu trữ, chia sẻ và truyền tệp nhanh hơn dễ dàng hơn.

#### Câu hỏi: Làm cách nào tôi có thể tắt tính năng nhúng phông chữ Windows vào tài liệu PDF bằng Aspose.Words cho .NET?
Trả lời: Để tắt tính năng nhúng phông chữ Windows vào tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Tải tài liệu bạn muốn chuyển đổi sang PDF bằng cách sử dụng`Document` đường dẫn lớp và tài liệu.

 Tạo một thể hiện của`PdfSaveOptions` lớp và thiết lập`FontEmbeddingMode`tài sản để`PdfFontEmbeddingMode.EmbedNone`. Điều này vô hiệu hóa việc nhúng phông chữ Windows vào tệp PDF được tạo.

 Sử dụng`Save` phương pháp của`Document` đối tượng chuyển đổi tài liệu sang PDF chỉ định các tùy chọn chuyển đổi được định cấu hình trước đó.

#### Hỏi: Lợi ích của việc tắt tính năng nhúng phông chữ Windows vào tài liệu PDF là gì?
Trả lời: Lợi ích của việc tắt tính năng nhúng phông chữ Windows vào tài liệu PDF là:

Giảm kích thước tệp PDF: Bằng cách vô hiệu hóa tính năng nhúng phông chữ của Windows, dữ liệu phông chữ Windows được nhúng sẽ bị xóa, làm giảm kích thước của tệp PDF được tạo.

Lưu trữ dễ dàng hơn: Các tệp PDF nhỏ hơn sẽ dễ dàng lưu trữ, lưu và chuyển hơn.

Chia sẻ và truyền tải nhanh hơn: Các tệp PDF nhỏ hơn có thể được chia sẻ và truyền tải nhanh hơn, tiết kiệm thời gian và tài nguyên.

#### Hỏi: Hậu quả của việc tắt tính năng nhúng phông chữ Windows vào tài liệu PDF là gì?
Trả lời: Việc tắt tính năng nhúng phông chữ Windows vào tài liệu PDF có thể dẫn đến những hậu quả như:

Mất hình thức và định dạng: Nếu phông chữ Windows được chỉ định trong tài liệu không có sẵn trên hệ thống nơi tệp PDF được mở, các phông chữ thay thế sẽ được sử dụng, điều này có thể dẫn đến hình thức và định dạng không chính xác. có hình dạng khác với những gì được mong đợi.

Vấn đề về khả năng đọc: Nếu phông chữ thay thế được sử dụng không dễ đọc như phông chữ gốc thì điều đó có thể ảnh hưởng đến khả năng đọc văn bản trong tài liệu PDF.