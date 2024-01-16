---
title: Giảm kích thước tệp PDF bằng cách không nhúng phông chữ cốt lõi
linktitle: Giảm kích thước tệp PDF bằng cách không nhúng phông chữ cốt lõi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách Giảm kích thước tệp PDF bằng cách không nhúng phông chữ cốt lõi khi chuyển đổi tài liệu Word sang PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước cách giảm kích thước tệp PDF bằng cách không nhúng các phông chữ cốt lõi bằng Aspose.Words cho .NET. Tính năng này cho phép bạn kiểm soát xem có phải nhúng các phông chữ cơ bản như Arial, Times New Roman, v.v. vào tệp PDF khi chuyển đổi tài liệu Word hay không. Làm theo các bước dưới đây:

## Bước 1: Tải tài liệu

Bắt đầu bằng cách tải lên tài liệu Word mà bạn muốn chuyển đổi sang PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Đảm bảo chỉ định đường dẫn chính xác tới tài liệu Word của bạn.

## Bước 2: Đặt tùy chọn chuyển đổi PDF

Tạo một phiên bản của lớp PdfSaveOptions và kích hoạt tính năng tránh nhúng phông chữ cơ bản:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Tùy chọn này kiểm soát xem có nên nhúng phông chữ cơ bản vào tệp PDF hay không.

## Bước 3: Chuyển đổi tài liệu sang PDF

 Sử dụng`Save` phương pháp chuyển đổi tài liệu Word sang PDF bằng cách chỉ định các tùy chọn chuyển đổi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Đảm bảo chỉ định đường dẫn chính xác để lưu tệp PDF đã chuyển đổi.

### Mã nguồn ví dụ về Tránh nhúng phông chữ lõi bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để sử dụng tính năng tránh nhúng phông chữ cốt lõi với Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Tệp PDF đầu ra sẽ không được nhúng với các phông chữ cốt lõi như Arial, Times New Roman, v.v.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng kiểm soát xem có nên nhúng phông chữ cơ sở vào tệp PDF hay không khi chuyển đổi tài liệu Word bằng Aspose.Words cho .NET.


## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách giảm kích thước tệp PDF bằng cách không nhúng các phông chữ cơ bản bằng Aspose.Words cho .NET. Tính năng này cho phép bạn kiểm soát xem có nên nhúng phông chữ cơ bản vào PDF khi chuyển đổi tài liệu Word hay không. Bằng cách làm theo các bước đã nêu, bạn có thể dễ dàng kiểm soát việc nhúng hoặc không nhúng các phông chữ cơ bản, điều này có thể giúp giảm kích thước tệp PDF và đảm bảo khả năng tương thích tốt hơn cũng như giao diện tài liệu nhất quán trên các thiết bị và nền tảng khác nhau. Đừng quên xem xét hậu quả của việc không nhúng phông chữ cơ bản và thử nghiệm để đảm bảo rằng tài liệu hiển thị như mong đợi.

### Các câu hỏi thường gặp

#### Hỏi: Tùy chọn không nhúng phông chữ cơ bản vào tệp PDF là gì và tại sao tùy chọn này lại quan trọng?
Trả lời: Tùy chọn không nhúng phông chữ cơ bản vào tệp PDF sẽ kiểm soát xem các phông chữ cơ sở như Arial, Times New Roman, v.v. có phải được nhúng vào tệp PDF khi chuyển đổi tài liệu Word hay không. Điều này có thể quan trọng để giảm kích thước tệp PDF bằng cách tránh bao gồm các phông chữ thường có sẵn trên hệ thống đọc PDF. Nó cũng có thể giúp đảm bảo khả năng tương thích tốt hơn và sự xuất hiện nhất quán của tài liệu PDF trên các thiết bị và nền tảng khác nhau.

#### Câu hỏi: Làm cách nào tôi có thể định cấu hình Aspose.Words để .NET không nhúng phông chữ cơ bản vào tệp PDF?
Trả lời: Để định cấu hình Aspose.Words cho .NET không nhúng các phông chữ cốt lõi vào tệp PDF, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENTS DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu Word bạn muốn chuyển đổi sang PDF bằng cách sử dụng`Document` lớp và đường dẫn tài liệu được chỉ định.

 Tạo một thể hiện của`PdfSaveOptions` lớp và thiết lập`UseCoreFonts`tài sản để`true`. Điều này sẽ tránh việc nhúng phông chữ cơ bản vào tệp PDF được tạo.

 Sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu ở định dạng PDF chỉ định các tùy chọn chuyển đổi được định cấu hình trước đó.

#### Câu hỏi: Lợi ích của việc không nhúng phông chữ cơ bản vào tệp PDF là gì?
Trả lời: Lợi ích của việc không nhúng phông chữ cơ bản vào tệp PDF là:

Giảm kích thước tệp PDF: Bằng cách tránh nhúng các phông chữ phổ biến có sẵn như Arial, Times New Roman, v.v., kích thước tệp PDF có thể được giảm xuống, giúp lưu trữ, chia sẻ và truyền tệp dễ dàng hơn.

Khả năng tương thích tốt hơn: Bằng cách sử dụng các phông chữ cơ bản thường có trên hệ thống đọc PDF, bạn đảm bảo khả năng tương thích và xuất hiện tài liệu tốt hơn trên các thiết bị và nền tảng khác nhau.

#### Hỏi: Hậu quả của việc không nhúng phông chữ cơ bản vào tệp PDF là gì?
Trả lời: Hậu quả của việc không nhúng phông chữ cơ bản vào tệp PDF như sau:

Hình thức khác: Nếu phông chữ cơ bản không có sẵn trên hệ thống nơi tệp PDF được mở, phông chữ thay thế sẽ được sử dụng, điều này có thể dẫn đến hình thức khác với dự định.

Vấn đề về khả năng đọc: Phông chữ thay thế được sử dụng có thể không dễ đọc như phông chữ gốc, điều này có thể ảnh hưởng đến khả năng đọc của tài liệu.