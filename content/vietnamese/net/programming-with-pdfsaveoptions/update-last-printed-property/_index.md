---
title: Cập nhật thuộc tính được in lần cuối trong tài liệu PDF
linktitle: Cập nhật thuộc tính được in lần cuối trong tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để cập nhật thuộc tính "Bản in cuối cùng" khi chuyển đổi sang PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/update-last-printed-property/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng thuộc tính "In lần cuối" trong tính năng cập nhật Tài liệu PDF với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Ở cuối hướng dẫn này, bạn sẽ có thể hiểu cách định cấu hình tùy chọn cập nhật thuộc tính "Được in lần cuối" khi chuyển đổi sang PDF.

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

## Bước 3: Định cấu hình tùy chọn Lưu dưới dạng PDF với thuộc tính "In lần cuối" được cập nhật

 Để bật cập nhật thuộc tính "Bản in cuối cùng" khi chuyển đổi sang PDF, chúng ta cần định cấu hình`PdfSaveOptions` đối tượng và thiết lập`UpdateLastPrintedProperty`tài sản để`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };
```

## Bước 4: Lưu tài liệu dưới dạng PDF với bản cập nhật thuộc tính "Được in lần cuối"

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng PDF bằng cách sử dụng các tùy chọn lưu đã định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);
```

Đó là tất cả ! Bạn đã kích hoạt thành công việc cập nhật thuộc tính "Bản in cuối cùng" khi chuyển đổi tài liệu sang PDF bằng Aspose.Words for .NET.

### Mã nguồn ví dụ để cập nhật thuộc tính "Được in lần cuối" với Aspose.Words cho .NET


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { UpdateLastPrintedProperty = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.UpdateIfLastPrinted.pdf", saveOptions);

```
## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách cập nhật thuộc tính "Bản in cuối cùng" trong tài liệu PDF bằng Aspose.Words cho .NET. Bằng cách làm theo các bước đã cho, bạn có thể dễ dàng định cấu hình tùy chọn cập nhật thuộc tính "Được in lần cuối" khi chuyển đổi tài liệu sang PDF. Sử dụng tính năng này để theo dõi việc sử dụng tài liệu và thông tin liên quan.

### Các câu hỏi thường gặp

#### Câu hỏi: Thuộc tính "Bản in cuối cùng" trong tài liệu PDF là gì?
Trả lời: Thuộc tính "Được in lần cuối" trong tài liệu PDF đề cập đến ngày và giờ tài liệu được in lần cuối. Thuộc tính này có thể hữu ích để theo dõi thông tin về việc sử dụng và quản lý tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể cập nhật thuộc tính "Bản in cuối cùng" trong tài liệu PDF bằng Aspose.Words cho .NET?
Trả lời: Để cập nhật thuộc tính "Bản in cuối cùng" trong tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Tạo một thể hiện của`Document` lớp chỉ định đường dẫn đến tài liệu Word.

 Tạo một thể hiện của`PdfSaveOptions` lớp và thiết lập`UpdateLastPrintedProperty`tài sản để`true` để cho phép cập nhật thuộc tính "Được in lần cuối".

 Sử dụng`Save` phương pháp của`Document`lớp để lưu tài liệu ở định dạng PDF bằng cách chỉ định các tùy chọn lưu.

#### Câu hỏi: Làm cách nào để kiểm tra xem thuộc tính "Bản in lần cuối" đã được cập nhật trong tài liệu PDF được tạo chưa?
Trả lời: Bạn có thể kiểm tra xem thuộc tính "Bản in cuối cùng" đã được cập nhật trong tài liệu PDF được tạo hay chưa bằng cách mở tệp PDF bằng trình xem PDF tương thích, chẳng hạn như Adobe Acrobat Reader và xem thông tin tài liệu. Ngày và giờ của lần in cuối cùng phải tương ứng với ngày và giờ tạo tài liệu PDF.
