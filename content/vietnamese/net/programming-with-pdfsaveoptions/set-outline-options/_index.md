---
title: Đặt tùy chọn phác thảo trong tài liệu PDF
linktitle: Đặt tùy chọn phác thảo trong tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để đặt tùy chọn phác thảo trong tài liệu PDF với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/set-outline-options/
---

Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng các tùy chọn phác thảo đã đặt cho tính năng kích thước siêu tệp với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách đặt tùy chọn phác thảo trong tài liệu và tạo tệp PDF với các tùy chọn phác thảo tương ứng.

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

## Bước 3: Định cấu hình tùy chọn lưu dưới dạng PDF với các tùy chọn gói

 Để đặt các tùy chọn phác thảo trong tệp PDF được tạo, chúng ta cần định cấu hình`PdfSaveOptions` sự vật. Chúng ta có thể đặt số lượng cấp độ phác thảo tiêu đề (`HeadingsOutlineLevels`) và số lượng cấp độ phác thảo mở rộng (`ExpandedOutlineLevels`).

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## Bước 4: Lưu tài liệu dưới dạng PDF với các tùy chọn phác thảo

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng PDF bằng cách sử dụng các tùy chọn lưu đã định cấu hình trước đó.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

Đó là tất cả ! Bạn đã đặt thành công các tùy chọn phác thảo trong tài liệu và tạo tệp PDF có các tùy chọn phác thảo tương ứng bằng Aspose.Words cho .NET.

### Mã nguồn ví dụ để đặt tùy chọn gói thành kích thước siêu tệp với Aspose.Words cho .NET


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã giải thích cách đặt tùy chọn phác thảo trong tài liệu PDF bằng Aspose.Words cho .NET. Sử dụng các bước được mô tả, bạn có thể dễ dàng chỉ định cấp độ tiêu đề và phác thảo trong tài liệu của mình và tạo tệp PDF với các tùy chọn phác thảo tương ứng. Tận hưởng những lợi ích của tùy chọn phác thảo để cải thiện cấu trúc và điều hướng trong tài liệu PDF của bạn bằng Aspose.Words for .NET.

### Các câu hỏi thường gặp

#### Hỏi: Tùy chọn phác thảo trong tài liệu PDF là gì?
Đáp: Tùy chọn phác thảo trong tài liệu PDF đề cập đến cấu trúc phân cấp của nội dung tài liệu. Nó cho phép bạn tạo một mục lục tương tác và tạo điều kiện thuận lợi cho việc điều hướng trong tài liệu. Các tùy chọn dàn bài xác định mức tiêu đề và phụ đề cần đưa vào dàn bài và mức độ chi tiết sẽ hiển thị trong dàn bài được tạo.

#### Câu hỏi: Làm cách nào tôi có thể đặt tùy chọn phác thảo trong tài liệu PDF bằng Aspose.Words cho .NET?
Trả lời: Để đặt các tùy chọn phác thảo trong tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tải tài liệu bạn muốn chuyển đổi sang PDF bằng cách sử dụng`Document` lớp và chỉ định đường dẫn đến tài liệu trong thư mục tài liệu đã chỉ định.

 Định cấu hình tùy chọn lưu dưới dạng PDF bằng cách tạo một phiên bản của`PdfSaveOptions` lớp và sử dụng`OutlineOptions` thuộc tính để đặt các tùy chọn phác thảo. Bạn có thể chỉ định số cấp tiêu đề cần đưa vào dàn bài bằng cách sử dụng`HeadingsOutlineLevels` thuộc tính và số lượng cấp độ phác thảo mở rộng bằng cách sử dụng`ExpandedOutlineLevels` tài sản.

 Lưu tài liệu ở định dạng PDF bằng cách sử dụng`Save` phương pháp của`Document` lớp chỉ định đường dẫn và các tùy chọn lưu.

#### Câu hỏi: Tùy chọn kế hoạch trong tài liệu PDF là gì?
Trả lời: Tùy chọn phác thảo trong tài liệu PDF cho phép bạn tạo cấu trúc phân cấp của nội dung, giúp điều hướng tài liệu và truy cập các phần khác nhau dễ dàng hơn. Điều này cho phép người dùng nhanh chóng chuyển đến các phần cụ thể của tài liệu bằng cách nhấp vào các mục trong mục lục hoặc dàn ý. Tùy chọn phác thảo cũng nâng cao trải nghiệm đọc bằng cách cung cấp cái nhìn tổng quan về cấu trúc tài liệu tổng thể.
