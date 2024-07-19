---
title: Tách tài liệu Word theo phần HTML
linktitle: Theo phần Html
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chia tài liệu Word thành các phần Html bằng Aspose.Words cho .NET với ví dụ về mã hoàn chỉnh.
type: docs
weight: 10
url: /vi/net/split-document/by-sections-html/
---

Trong ví dụ này, chúng tôi sẽ chỉ cho bạn cách chia tài liệu Word thành các phần riêng biệt ở định dạng HTML bằng cách sử dụng tính năng Theo phần HTML của Aspose.Words cho .NET. Thực hiện theo các bước bên dưới để hiểu mã nguồn và tạo tài liệu HTML riêng cho từng phần.

## Bước 1: Tải tài liệu

Để bắt đầu, hãy chỉ định thư mục cho tài liệu của bạn và tải tài liệu vào đối tượng Tài liệu. Đây là cách thực hiện:

```csharp
//Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Bước 2: Chia tài liệu thành các phần ở định dạng HTML

Bây giờ chúng ta sẽ đặt các tùy chọn lưu để chia tài liệu thành các phần ở định dạng HTML. Đây là cách thực hiện:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Mã nguồn mẫu cho HTML theo phần sử dụng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho tính năng Theo phần HTML của Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

Với mã này, bạn sẽ có thể chia tài liệu Word thành các phần riêng biệt ở định dạng HTML bằng Aspose.Words for .NET.

Bây giờ bạn có thể tạo các tài liệu HTML riêng biệt cho từng phần của tài liệu ban đầu.

## Phần kết luận

Trong hướng dẫn này, chúng ta đã học cách chia tài liệu Word thành các phần riêng biệt ở định dạng HTML bằng cách sử dụng tính năng Theo phần HTML của Aspose.Words cho .NET. Bằng cách làm theo mã nguồn được cung cấp, bạn có thể tạo các tài liệu HTML riêng lẻ cho từng phần của tài liệu gốc.

Việc chia tài liệu thành các phần có thể hữu ích cho nhiều mục đích khác nhau như tạo trang web, trích xuất nội dung cụ thể hoặc sắp xếp thông tin. Aspose.Words for .NET cung cấp một API mạnh mẽ cho phép bạn thao tác và tùy chỉnh tài liệu Word theo yêu cầu của mình.

Vui lòng khám phá các tính năng bổ sung do Aspose.Words cho .NET cung cấp để nâng cao hơn nữa khả năng xử lý tài liệu và cải thiện quy trình làm việc của bạn.

### Câu hỏi thường gặp

#### Làm cách nào tôi có thể tùy chỉnh định dạng đầu ra HTML?

Aspose.Words for .NET cung cấp nhiều tùy chọn khác nhau để tùy chỉnh định dạng đầu ra HTML. Bạn có thể sửa đổi kiểu dáng, cài đặt phông chữ, độ phân giải hình ảnh và nhiều khía cạnh khác của tài liệu HTML bằng cách điều chỉnh các tùy chọn lưu. Tham khảo tài liệu Aspose.Words for .NET để biết thông tin chi tiết về các tùy chọn có sẵn và cách sử dụng chúng.

#### Tôi có thể chia tài liệu dựa trên tiêu chí khác không?

Có, ngoài việc sử dụng dấu ngắt phần làm tiêu chí phân chia, Aspose.Words for .NET còn cung cấp các tùy chọn khác như ngắt đoạn, kiểu tiêu đề hoặc nội dung cụ thể làm tiêu chí để phân chia tài liệu. Bạn có thể chọn tiêu chí phù hợp nhất dựa trên yêu cầu của mình và điều chỉnh mã cho phù hợp.

#### Có thể chia tài liệu thành các định dạng khác ngoài HTML không?

Có, Aspose.Words for .NET hỗ trợ chia tài liệu thành nhiều định dạng khác nhau bao gồm PDF, văn bản thuần túy, hình ảnh, v.v. Bạn có thể sửa đổi các tùy chọn lưu để tạo định dạng đầu ra mong muốn. Tham khảo tài liệu Aspose.Words for .NET để biết thêm chi tiết về các định dạng có sẵn và cách chỉ định chúng trong các tùy chọn lưu.

#### Tôi có thể chia nhiều tài liệu cùng một lúc không?

Có, bạn có thể áp dụng đồng thời quy trình phân tách cho nhiều tài liệu bằng cách lặp qua một tập hợp tài liệu và thực thi mã phân tách cho từng tài liệu riêng lẻ. Điều này cho phép bạn xử lý hiệu quả nhiều tài liệu và tạo các phần riêng biệt cho từng tài liệu.

#### Làm cách nào tôi có thể hợp nhất các phần lại thành một tài liệu?

Aspose.Words for .NET cũng cung cấp các phương thức để hợp nhất nhiều tài liệu hoặc phần lại thành một tài liệu. Bằng cách sử dụng các tính năng hợp nhất này, bạn có thể kết hợp các phần được tạo riêng biệt và tạo thành một tài liệu thống nhất. Tham khảo tài liệu Aspose.Words for .NET để biết thêm thông tin về cách hợp nhất các tài liệu hoặc phần.


