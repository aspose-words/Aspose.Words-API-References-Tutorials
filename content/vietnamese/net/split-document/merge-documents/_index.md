---
title: Hợp nhất tài liệu Word
linktitle: Hợp nhất tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hợp nhất nhiều tài liệu Word bằng Aspose.Words cho .NET. API mạnh mẽ này đơn giản hóa quá trình hợp nhất các tài liệu, làm cho nó hiệu quả và đơn giản.
type: docs
weight: 10
url: /vi/net/split-document/merge-documents/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách hợp nhất nhiều tài liệu Word bằng tính năng Hợp nhất Tài liệu của Aspose.Words cho .NET. Thực hiện theo các bước bên dưới để hiểu mã nguồn và nhận tài liệu được hợp nhất chứa tất cả tài liệu nguồn.

## Bước 1: Tìm kiếm tài liệu cần ghép

Trước khi hợp nhất các tài liệu, chúng ta cần xác định vị trí các tài liệu nguồn cần hợp nhất. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
// Tìm kiếm tài liệu để hợp nhất.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
.GetFileSystemInfos("SplitDocument.PageParPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
Directory.GetFiles(dataDir, "SplitDocument.PageParPage_1.docx", SearchOption.TopDirectoryOnly)[0];
```

## Bước 2: Hợp nhất tài liệu

Bây giờ chúng ta sẽ hợp nhất từng tài liệu một để tạo thành tài liệu hợp nhất cuối cùng. Đây là cách thực hiện:

```csharp
// Mở phần đầu tiên của tài liệu kết quả.
Document sourceDoc = new Document(sourceDocumentPath);

// Tạo một tài liệu kết quả mới.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Hợp nhất từng tài liệu một.
foreach(FileSystemInfo documentPath in documentPaths)
{
if (documentPath.FullName == sourceDocumentPath)
keep on going;

mergedDocBuilder.MoveToDocumentEnd();
mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

### Mã nguồn mẫu cho Hợp nhất tài liệu bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho tính năng Hợp nhất Tài liệu của Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tìm tài liệu sử dụng để hợp nhất.
FileSystemInfo[] documentPaths = new DirectoryInfo(dataDir)
	.GetFileSystemInfos("SplitDocument.PageByPage_*.docx").OrderBy(f => f.CreationTime).ToArray();
string sourceDocumentPath =
	Directory.GetFiles(dataDir, "SplitDocument.PageByPage_1.docx", SearchOption.TopDirectoryOnly)[0];

// Mở phần đầu tiên của tài liệu kết quả.
Document sourceDoc = new Document(sourceDocumentPath);

// Tạo một tài liệu kết quả mới.
Document mergedDoc = new Document();
DocumentBuilder mergedDocBuilder = new DocumentBuilder(mergedDoc);

// Hợp nhất từng phần tài liệu một.
foreach (FileSystemInfo documentPath in documentPaths)
{
	if (documentPath.FullName == sourceDocumentPath)
		continue;

	mergedDocBuilder.MoveToDocumentEnd();
	mergedDocBuilder.InsertDocument(sourceDoc, ImportFormatMode.KeepSourceFormatting);
	sourceDoc = new Document(documentPath.FullName);
}

mergedDoc.Save(dataDir + "SplitDocument.MergeDocuments.docx");
```

## Phần kết luận

Chúc mừng! Bạn đã học cách hợp nhất nhiều tài liệu Word bằng tính năng Hợp nhất Tài liệu của Aspose.Words cho .NET. Bằng cách tuân theo mã nguồn được cung cấp, bạn có thể kết hợp các tài liệu riêng biệt thành một tài liệu được hợp nhất duy nhất trong khi vẫn giữ nguyên định dạng của từng tài liệu nguồn.

Việc hợp nhất các tài liệu có thể hữu ích khi bạn muốn hợp nhất thông tin từ nhiều nguồn hoặc tạo một tài liệu hợp nhất từ các phần riêng lẻ. Aspose.Words for .NET cung cấp một API mạnh mẽ giúp đơn giản hóa quá trình hợp nhất các tài liệu, giúp quá trình này trở nên hiệu quả và đơn giản.

Vui lòng khám phá các tính năng khác do Aspose.Words for .NET cung cấp để nâng cao khả năng xử lý tài liệu và hợp lý hóa quy trình làm việc của bạn.

### Câu hỏi thường gặp

#### Làm cách nào để hợp nhất các tài liệu có định dạng khác nhau?

 Khi hợp nhất các tài liệu, Aspose.Words for .NET cung cấp tùy chọn giữ nguyên định dạng của từng tài liệu nguồn. Bằng cách sử dụng`ImportFormatMode.KeepSourceFormatting` tùy chọn, tài liệu được hợp nhất sẽ giữ lại định dạng của tài liệu gốc. Nếu muốn áp dụng định dạng nhất quán trong toàn bộ tài liệu đã hợp nhất, bạn có thể sửa đổi định dạng bằng API Aspose.Words sau khi hợp nhất các tài liệu.

#### Tôi có thể hợp nhất các tài liệu ở các định dạng khác nhau không?

Có, Aspose.Words for .NET hỗ trợ hợp nhất các tài liệu ở nhiều định dạng khác nhau, bao gồm DOCX, DOC, RTF, v.v. Bạn có thể tải các tài liệu có định dạng khác nhau vào API Aspose.Words và hợp nhất chúng thành một tài liệu duy nhất bất kể định dạng ban đầu của chúng là gì.

#### Tôi có thể hợp nhất các tài liệu có cấu trúc phức tạp như bảng và hình ảnh không?

Tuyệt đối! Aspose.Words for .NET có khả năng hợp nhất các tài liệu có cấu trúc phức tạp, bao gồm bảng, hình ảnh, đầu trang, chân trang, v.v. API xử lý quá trình hợp nhất trong khi vẫn duy trì tính toàn vẹn và bố cục của nội dung trong mỗi tài liệu.

#### Có thể hợp nhất các tài liệu có hướng hoặc kích thước trang khác nhau không?

Có, Aspose.Words for .NET xử lý các tài liệu có hướng hoặc kích thước trang khác nhau trong quá trình hợp nhất. Tài liệu được hợp nhất thu được sẽ phù hợp với các hướng và kích thước trang khác nhau của tài liệu nguồn.