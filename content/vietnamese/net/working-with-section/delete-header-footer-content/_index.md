---
title: Xóa nội dung Header Footer
linktitle: Xóa nội dung Header Footer
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, hãy tìm hiểu cách xóa nội dung đầu trang và chân trang khỏi tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-section/delete-header-footer-content/
---

Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách xóa nội dung đầu trang và chân trang khỏi tài liệu Word bằng thư viện Aspose.Words cho .NET. Xóa nội dung khỏi đầu trang và chân trang có thể hữu ích khi bạn muốn đặt lại hoặc xóa các thành phần này khỏi tài liệu của mình. Chúng tôi sẽ hướng dẫn bạn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của mình.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn
- Tài liệu Word chứa đầu trang và chân trang mà bạn muốn loại bỏ

## Bước 1: Xác định thư mục tài liệu
 Trước tiên, bạn cần đặt đường dẫn thư mục đến vị trí tài liệu Word của mình. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Load tài liệu và vào phần
 Tiếp theo, chúng ta sẽ tải tài liệu Word vào một phiên bản của`Document` lớp học. Chúng ta sẽ truy cập phần đầu tiên của tài liệu bằng chỉ mục 0.

```csharp
// Tải tài liệu
Document doc = new Document(dataDir + "Document.docx");

// Truy cập phần
Section section = doc.Sections[0];
```

## Bước 3: Xóa nội dung header và footer
 Để xóa nội dung đầu trang và chân trang khỏi phần, chúng tôi sẽ sử dụng`ClearHeadersFooters` phương pháp.

```csharp
section.ClearHeadersFooters();
```

### Mã nguồn mẫu để Xóa nội dung chân trang bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
Section section = doc.Sections[0];
section.ClearHeadersFooters();

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã biết cách xóa nội dung đầu trang và chân trang khỏi tài liệu Word bằng Aspose.Words cho .NET. Xóa nội dung khỏi đầu trang và chân trang cho phép bạn đặt lại hoặc xóa các thành phần cụ thể đó khỏi tài liệu của mình. Vui lòng tùy chỉnh và sử dụng tính năng này theo nhu cầu cụ thể của bạn.

### Câu hỏi thường gặp về xóa nội dung chân trang đầu trang

#### Hỏi: Làm cách nào để đặt thư mục tài liệu trong Aspose.Words cho .NET?

 Đáp: Để đặt đường dẫn tới thư mục chứa tài liệu của bạn, bạn phải thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

#### Hỏi: Làm cách nào để tải tài liệu và phần truy cập trong Aspose.Words cho .NET?

 Đáp: Để tải tài liệu Word vào một phiên bản của`Document` lớp được gọi là`doc` và truy cập phần đầu tiên của tài liệu bằng chỉ mục 0, bạn có thể sử dụng mã sau:

```csharp
// Tải tài liệu
Document doc = new Document(dataDir + "Document.docx");

// Truy cập phần
Section section = doc.Sections[0];
```

#### Hỏi: Làm cách nào để xóa nội dung đầu trang và chân trang trong Aspose.Words cho .NET?

 Trả lời: Để xóa nội dung đầu trang và chân trang khỏi phần, bạn có thể sử dụng`ClearHeadersFooters` phương pháp:

```csharp
section.ClearHeadersFooters();
```

#### Hỏi: Làm cách nào để lưu tài liệu đã sửa đổi trong Aspose.Words cho .NET?

Trả lời: Khi bạn đã xóa nội dung đầu trang và chân trang, bạn có thể lưu tài liệu đã sửa đổi vào một tệp bằng mã sau:

```csharp
doc.Save(dataDir + "Document_Modified.docx");
```