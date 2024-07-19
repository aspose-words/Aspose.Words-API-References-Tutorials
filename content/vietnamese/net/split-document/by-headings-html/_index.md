---
title: Tách tài liệu Word theo tiêu đề Html
linktitle: Theo tiêu đề Html
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước giải thích mã nguồn C# của tài liệu word được chia tách Bằng tính năng HTML Heading của Aspose.Words for .NET
type: docs
weight: 10
url: /vi/net/split-document/by-headings-html/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách chia tài liệu Word thành các phần nhỏ hơn bằng cách sử dụng tính năng By HTML Heading của Aspose.Words cho .NET. Thực hiện theo các bước bên dưới để hiểu mã nguồn và tạo các tài liệu HTML riêng biệt dựa trên Tiêu đề.

## Bước 1: Tải tài liệu

Để bắt đầu, hãy chỉ định thư mục cho tài liệu của bạn và tải tài liệu vào đối tượng Tài liệu. Đây là cách thực hiện:

```csharp
//Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Bước 2: Chia tài liệu theo Heading ở định dạng HTML

Bây giờ chúng ta sẽ thiết lập các tùy chọn lưu để chia tài liệu thành các phần nhỏ hơn dựa trên Heading ở định dạng HTML. Đây là cách thực hiện:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Chia tài liệu thành các phần nhỏ hơn, trong trường hợp này tách nó theo tiêu đề.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Mã nguồn mẫu cho HTML theo tiêu đề sử dụng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho tính năng By HTML Heading của Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Chia tài liệu thành các phần nhỏ hơn, trong trường hợp này là chia theo tiêu đề.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Với mã này, bạn sẽ có thể chia tài liệu Word thành các phần nhỏ hơn bằng cách sử dụng Aspose.Words for .NET, dựa trên các tiêu đề. Sau đó, bạn có thể tạo các tài liệu HTML riêng biệt cho từng phần.

## Phần kết luận

 Trong hướng dẫn này, chúng ta đã học cách chia tài liệu Word thành các phần nhỏ hơn bằng cách sử dụng tính năng By HTML Heading của Aspose.Words cho .NET. Bằng cách chỉ định`DocumentSplitCriteria` BẰNG`HeadingParagraph` bên trong`HtmlSaveOptions`, chúng tôi có thể tạo các tài liệu HTML riêng biệt dựa trên các tiêu đề có trong tài liệu gốc.

Việc chia tài liệu theo tiêu đề có thể hữu ích cho việc tổ chức và quản lý nội dung, đặc biệt là trong các tài liệu lớn có nhiều phần. Aspose.Words for .NET cung cấp giải pháp đáng tin cậy và hiệu quả để xử lý việc phân tách tài liệu và tạo đầu ra ở nhiều định dạng khác nhau.

Vui lòng khám phá các tính năng và tùy chọn bổ sung do Aspose.Words cho .NET cung cấp để nâng cao hơn nữa khả năng xử lý tài liệu của bạn và hợp lý hóa quy trình làm việc của bạn.

### Câu hỏi thường gặp

#### Làm cách nào tôi có thể chia tài liệu Word thành các phần nhỏ hơn dựa trên các tiêu đề bằng Aspose.Words cho .NET?

 Để phân chia tài liệu Word dựa trên các tiêu đề, bạn có thể sử dụng tính năng By HTML Heading của Aspose.Words cho .NET. Thực hiện theo mã nguồn được cung cấp và đặt`DocumentSplitCriteria` ĐẾN`HeadingParagraph` bên trong`HtmlSaveOptions` sự vật. Điều này sẽ chia tài liệu thành các phần nhỏ hơn ở mỗi tiêu đề.

#### Tôi có thể chia tài liệu Word thành những định dạng nào?

 Mã nguồn được cung cấp thể hiện việc chia tài liệu Word thành các phần nhỏ hơn ở định dạng HTML. Tuy nhiên, Aspose.Words for .NET hỗ trợ nhiều định dạng đầu ra khác nhau, bao gồm DOCX, PDF, EPUB, v.v. Bạn có thể sửa đổi mã và chỉ định định dạng đầu ra mong muốn trong`HtmlSaveOptions` đối tượng tương ứng.

#### Tôi có thể chọn tiêu chí khác để chia tài liệu không?

Có, bạn có thể chọn tiêu chí khác để chia tài liệu dựa trên yêu cầu của mình. Aspose.Words for .NET cung cấp một số tùy chọn tiêu chí, chẳng hạn như`HeadingParagraph`, `Page`, `Section` , và hơn thế nữa. Sửa đổi`DocumentSplitCriteria` tài sản ở`HtmlSaveOptions` đối tượng để lựa chọn tiêu chí phân chia thích hợp.

#### Làm cách nào tôi có thể tùy chỉnh HTML đầu ra cho các phần được chia nhỏ?

 Aspose.Words for .NET cho phép bạn tùy chỉnh HTML đầu ra cho các phần được phân tách bằng cách chỉ định các tùy chọn bổ sung trong phần`HtmlSaveOptions` sự vật. Bạn có thể kiểm soát nhiều khía cạnh khác nhau như kiểu CSS, hình ảnh, phông chữ, v.v. Tham khảo tài liệu Aspose.Words để biết thêm chi tiết về cách tùy chỉnh đầu ra HTML.

#### Tôi có thể chia tài liệu dựa trên nhiều tiêu chí không?

 Có, bạn có thể chia tài liệu dựa trên nhiều tiêu chí bằng cách kết hợp các tùy chọn tiêu chí tương ứng. Ví dụ: bạn có thể chia tài liệu theo cả tiêu đề và trang bằng cách đặt`DocumentSplitCriteria`tài sản để`HeadingParagraph | Page`. Thao tác này sẽ phân chia tài liệu theo từng tiêu đề và từng trang, tạo ra các phần nhỏ hơn dựa trên cả hai tiêu chí.