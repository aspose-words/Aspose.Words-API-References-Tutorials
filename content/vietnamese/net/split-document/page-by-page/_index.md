---
title: Tách tài liệu Word theo trang
linktitle: Tách tài liệu Word theo trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chia tài liệu Word thành các trang riêng lẻ bằng Aspose.Words cho .NET. API mạnh mẽ này giúp đơn giản hóa quá trình chia nhỏ tài liệu, giúp nó hiệu quả và thuận tiện.
type: docs
weight: 10
url: /vi/net/split-document/page-by-page/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách chia tài liệu Word thành các trang riêng lẻ bằng tính năng xử lý tài liệu của Aspose.Words cho .NET. Hãy thực hiện theo các bước bên dưới để hiểu mã nguồn và nhận tài liệu riêng cho từng trang.

## Bước 1: Tải tài liệu

Để bắt đầu, hãy chỉ định thư mục cho tài liệu của bạn và tải tài liệu vào đối tượng Tài liệu. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Bước 2: Tách tài liệu theo trang

Bây giờ chúng ta sẽ duyệt qua từng trang của tài liệu và chia tài liệu thành các trang riêng lẻ. Đây là cách thực hiện:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Lưu mỗi trang dưới dạng một tài liệu riêng biệt.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Mã nguồn mẫu cho từng trang sử dụng Aspose.Words for .NET

Đây là mã nguồn hoàn chỉnh cho tính năng từng trang của Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	// Lưu mỗi trang dưới dạng một tài liệu riêng biệt.
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

Với mã này, bạn sẽ có thể chia tài liệu Word thành các trang riêng lẻ bằng Aspose.Words cho .NET. Bạn cũng có thể hợp nhất các tài liệu riêng biệt nếu cần.

## Phần kết luận

Chúc mừng! Bạn đã học cách chia tài liệu Word thành các trang riêng lẻ bằng tính năng từng trang của Aspose.Words cho .NET. Bằng cách làm theo mã nguồn được cung cấp, bạn có thể trích xuất từng trang của tài liệu và lưu chúng dưới dạng tài liệu riêng biệt.

Việc chia tài liệu theo trang có thể hữu ích khi bạn cần làm việc với các trang cụ thể hoặc phân phối nội dung một cách chi tiết. Aspose.Words for .NET cung cấp một API mạnh mẽ giúp đơn giản hóa quá trình chia nhỏ tài liệu, giúp nó hiệu quả và thuận tiện.

Vui lòng khám phá các tính năng khác do Aspose.Words for .NET cung cấp để nâng cao khả năng xử lý tài liệu và hợp lý hóa quy trình làm việc của bạn.

### Câu hỏi thường gặp

#### Làm cách nào tôi có thể chia tài liệu thành nhiều trang bằng Aspose.Words cho .NET?

 Để chia tài liệu thành nhiều trang, bạn có thể sử dụng`ExtractPages` phương thức của API Aspose.Words để lấy phạm vi trang. Bằng cách chỉ định trang bắt đầu và số trang cần trích xuất, bạn có thể tạo các tài liệu riêng cho từng trang.

#### Tôi có thể tùy chỉnh định dạng đầu ra khi chia tài liệu theo trang không?

Có, Aspose.Words for .NET hỗ trợ nhiều định dạng đầu ra khác nhau khi chia tài liệu theo trang. Bạn có thể lưu từng trang dưới dạng tài liệu riêng biệt ở các định dạng như DOCX, PDF, HTML, v.v., tùy thuộc vào yêu cầu của bạn.

#### Tôi có thể chia tài liệu theo phạm vi trang cụ thể không?

Tuyệt đối! Aspose.Words for .NET cho phép bạn chia tài liệu theo một phạm vi trang cụ thể. Bằng cách điều chỉnh trang bắt đầu và số lượng trang cần trích xuất, bạn có thể xác định chính xác phạm vi trang để chia tài liệu.

#### Có thể hợp nhất các tài liệu đã chia thành một tài liệu duy nhất không?

Có, bạn có thể hợp nhất các tài liệu đã tách lại thành một tài liệu duy nhất bằng cách sử dụng chức năng hợp nhất do Aspose.Words cho .NET cung cấp. Bằng cách kết hợp các tài liệu riêng biệt, bạn có thể tạo lại tài liệu gốc hoặc tạo tài liệu mới có cấu trúc khác, nếu cần.