---
title: Cảnh báo kết xuất Pdf
linktitle: Cảnh báo kết xuất Pdf
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để xử lý các cảnh báo hiển thị PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng tính năng cảnh báo hiển thị PDF với Aspose.Words dành cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách xử lý các cảnh báo hiển thị khi chuyển đổi sang PDF.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu lên

Tiếp theo, chúng ta cần tải tài liệu mà chúng ta muốn xử lý. Trong ví dụ này, chúng tôi giả sử tài liệu có tên là "WMF with image.docx" và nằm trong thư mục tài liệu được chỉ định.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Bước 3: Định cấu hình tùy chọn lưu dưới dạng PDF với cảnh báo kết xuất

 Để xử lý các cảnh báo hiển thị khi chuyển đổi sang PDF, chúng ta cần định cấu hình`MetafileRenderingOptions` đối tượng để chỉ định cách hiển thị siêu tệp. Chúng tôi cũng sử dụng`HandleDocumentWarnings` tùy chọn để xử lý các cảnh báo được tạo khi lưu tài liệu.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Bước 4: Lưu tài liệu dưới dạng PDF kèm theo cảnh báo kết xuất

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng PDF bằng cách sử dụng các tùy chọn lưu đã định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Bước 5: Xử lý cảnh báo kết xuất

Có thể truy xuất các cảnh báo hiển thị được tạo khi lưu tài liệu bằng trình xử lý cảnh báo tùy chỉnh. Trong ví dụ này, chúng tôi chỉ in mô tả của từng cảnh báo.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

Đó là tất cả ! Bạn đã xử lý thành công các cảnh báo hiển thị khi chuyển đổi tài liệu

  sang PDF bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho các cảnh báo hiển thị PDF với Aspose.Words for .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	//Nếu Aspose.Words không thể hiển thị chính xác một số bản ghi siêu tệp
	// sang đồ họa vector thì Aspose.Words sẽ hiển thị siêu tệp này thành bitmap.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Mặc dù lưu tệp thành công nhưng các cảnh báo hiển thị xảy ra trong quá trình lưu sẽ được thu thập tại đây.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```

### Các câu hỏi thường gặp

#### Câu hỏi: Chức năng của cảnh báo kết xuất PDF với Aspose.Words dành cho .NET là gì?
Tính năng Cảnh báo hiển thị PDF với Aspose.Words cho .NET giúp quản lý các cảnh báo được tạo khi chuyển đổi tài liệu sang PDF. Nó cung cấp một cách để phát hiện và giải quyết các cảnh báo kết xuất để đảm bảo chất lượng và tính toàn vẹn của tài liệu được chuyển đổi.

#### Câu hỏi: Làm cách nào tôi có thể sử dụng tính năng này với Aspose.Words cho .NET?
Để sử dụng tính năng này với Aspose.Words cho .NET, hãy làm theo các bước sau:

Đặt thư mục tài liệu bằng cách chỉ định đường dẫn thư mục chứa tài liệu của bạn.

 Tải tài liệu cần xử lý bằng cách sử dụng`Document` phương thức và chỉ định đường dẫn tệp.

 Định cấu hình các tùy chọn lưu vào PDF bằng cách tạo một phiên bản của`PdfSaveOptions` lớp học. Sử dụng`MetafileRenderingOptions` lớp để chỉ định cách hiển thị siêu tệp và đặt`MetafileRenderingOptions.RenderingMode` ĐẾN`MetafileRenderingMode.VectorWithFallback`.

 Sử dụng`HandleDocumentWarnings` lớp để xử lý các cảnh báo kết xuất. Bộ`doc.WarningCallback` đến một thể hiện của lớp này.

 Sử dụng`Save` phương pháp lưu tài liệu ở định dạng PDF chỉ định các tùy chọn lưu.

Sau đó, bạn có thể xử lý các cảnh báo kết xuất bằng cách sử dụng`HandleDocumentWarnings` lớp học. Ví dụ: bạn có thể hiển thị mô tả của từng cảnh báo bằng vòng lặp.

#### Hỏi: Làm cách nào để biết liệu có bất kỳ cảnh báo kết xuất nào khi chuyển đổi tài liệu sang PDF hay không?
 Bạn có thể dùng`HandleDocumentWarnings` class để truy xuất các cảnh báo hiển thị được tạo khi lưu tài liệu. Lớp này chứa một`mWarnings` list lưu trữ thông tin về cảnh báo. Bạn có thể duyệt qua danh sách này và truy cập các thuộc tính của từng cảnh báo, chẳng hạn như mô tả, để thực hiện hành động thích hợp.

#### Câu hỏi: Loại cảnh báo kết xuất nào có thể được tạo khi chuyển đổi sang PDF?
Hiển thị cảnh báo khi chuyển đổi sang PDF có thể bao gồm các cảnh báo liên quan đến bố cục, thiếu phông chữ, hình ảnh không được hỗ trợ, vấn đề tương thích, v.v. Các cảnh báo cụ thể sẽ phụ thuộc vào nội dung của tài liệu nguồn và các tùy chọn chuyển đổi được sử dụng.

#### Câu hỏi: Có thể xử lý cảnh báo kết xuất theo cách tùy chỉnh không?
 Có, bạn có thể tùy chỉnh việc xử lý cảnh báo hiển thị bằng cách tùy chỉnh`HandleDocumentWarnings`lớp học. Bạn có thể thêm chức năng bổ sung để quản lý các cảnh báo cụ thể cho ứng dụng của mình, chẳng hạn như ghi nhật ký cảnh báo, tạo báo cáo, gửi cảnh báo, v.v.