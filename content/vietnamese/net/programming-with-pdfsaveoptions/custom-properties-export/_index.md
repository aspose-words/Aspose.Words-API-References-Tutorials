---
title: Xuất thuộc tính tùy chỉnh trong tài liệu PDF
linktitle: Xuất thuộc tính tùy chỉnh trong tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xuất thuộc tính tùy chỉnh khi chuyển đổi tài liệu sang PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/custom-properties-export/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để xuất thuộc tính tùy chỉnh của tài liệu trong tài liệu PDF bằng Aspose.Words cho .NET. Xuất thuộc tính tùy chỉnh cho phép bạn đưa thông tin bổ sung vào tài liệu PDF được tạo. Làm theo các bước dưới đây:

## Bước 1: Tạo tài liệu và thêm thuộc tính tùy chỉnh

Bắt đầu bằng cách tạo một thể hiện của lớp Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Bước 2: Thêm thuộc tính tùy chỉnh
 Tiếp theo, thêm các thuộc tính tùy chỉnh mong muốn. Ví dụ: để thêm thuộc tính "Công ty" có giá trị "Aspose", hãy sử dụng thuộc tính`Add` phương thức của bộ sưu tập CustomDocumentProperties:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Bạn có thể thêm bao nhiêu thuộc tính tùy chỉnh nếu cần.

## Bước 3: Đặt tùy chọn xuất PDF

Tạo một phiên bản của lớp PdfSaveOptions và chỉ định cách xuất các thuộc tính tùy chỉnh:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Tùy chọn này kiểm soát việc xuất các thuộc tính tùy chỉnh khi chuyển đổi sang PDF.

## Bước 4: Chuyển đổi tài liệu sang PDF

 Sử dụng`Save` phương pháp chuyển đổi tài liệu sang PDF chỉ định các tùy chọn chuyển đổi:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Đảm bảo chỉ định đường dẫn chính xác để lưu tệp PDF đã chuyển đổi.

### Mã nguồn ví dụ cho Xuất thuộc tính tùy chỉnh bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để xuất các thuộc tính tùy chỉnh từ tài liệu bằng Aspose.Words cho .NET:


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng xuất các thuộc tính tùy chỉnh của tài liệu khi chuyển đổi sang PDF bằng Aspose.Words cho .NET.


## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách xuất các thuộc tính tùy chỉnh từ tài liệu sang tài liệu PDF bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được mô tả, bạn có thể dễ dàng đưa thông tin bổ sung vào tài liệu PDF được tạo bằng cách xuất các thuộc tính tùy chỉnh của tài liệu. Tận dụng các tính năng của Aspose.Words for .NET để cá nhân hóa và làm phong phú tài liệu PDF của bạn bằng cách xuất các thuộc tính tùy chỉnh.

### Các câu hỏi thường gặp

#### Câu hỏi: Xuất thuộc tính tùy chỉnh sang tài liệu PDF là gì?
Đáp: Việc xuất các thuộc tính tùy chỉnh sang tài liệu PDF cho phép đưa thông tin bổ sung vào tài liệu PDF được tạo. Thuộc tính tùy chỉnh là siêu dữ liệu dành riêng cho tài liệu của bạn, chẳng hạn như thẻ, từ khóa hoặc thông tin xác thực. Bằng cách xuất các thuộc tính tùy chỉnh này, bạn có thể cung cấp chúng cho người dùng khi xem tài liệu PDF.

#### Câu hỏi: Làm cách nào tôi có thể xuất các thuộc tính tùy chỉnh của tài liệu sang tài liệu PDF bằng Aspose.Words cho .NET?
Trả lời: Để xuất các thuộc tính tùy chỉnh của tài liệu sang tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Tạo một thể hiện của`Document` lớp học.

 Thêm các thuộc tính tùy chỉnh mong muốn bằng cách sử dụng`CustomDocumentProperties` bộ sưu tập. Ví dụ, sử dụng`Add` để thêm thuộc tính "Công ty" có giá trị "Aspose".

 Tạo một thể hiện của`PdfSaveOptions` lớp và chỉ định cách xuất các thuộc tính tùy chỉnh bằng cách sử dụng`CustomPropertiesExport` tài sản. Các`PdfCustomPropertiesExport.Standard` value xuất các thuộc tính tùy chỉnh theo cài đặt mặc định.

 Sử dụng`Save` phương pháp của`Document` lớp để chuyển đổi tài liệu sang PDF chỉ định các tùy chọn chuyển đổi.

#### Hỏi: Làm cách nào tôi có thể truy cập các thuộc tính tùy chỉnh của tài liệu PDF?
Trả lời: Để truy cập các thuộc tính tùy chỉnh của tài liệu PDF, bạn có thể sử dụng trình đọc PDF tương thích hỗ trợ xem các thuộc tính tài liệu. Hầu hết các trình đọc PDF phổ biến, chẳng hạn như Adobe Acrobat Reader, cung cấp quyền truy cập vào siêu dữ liệu và thuộc tính của tài liệu PDF. Bạn thường có thể tìm thấy các tùy chọn này trong menu "Tệp" hoặc bằng cách nhấp chuột phải vào tài liệu và chọn "Thuộc tính".