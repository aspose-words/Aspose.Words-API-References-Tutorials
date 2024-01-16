---
title: Kiểm tra hiệu ứng văn bản DrawML
linktitle: Kiểm tra hiệu ứng văn bản DrawML
second_title: API xử lý tài liệu Aspose.Words
description: Trong hướng dẫn này, hãy tìm hiểu cách kiểm tra hiệu ứng văn bản DrawML trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fonts/check-drawingml-text-effect/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách kiểm tra hiệu ứng văn bản DrawML trong tài liệu Word bằng Thư viện Aspose.Words cho .NET. Kiểm tra hiệu ứng văn bản DrawML cho phép bạn xác định xem một hiệu ứng cụ thể có được áp dụng cho một phần văn bản hay không. Chúng tôi sẽ hướng dẫn bạn từng bước để giúp bạn hiểu và triển khai mã trong dự án .NET của mình.

## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có các mục sau:
- Kiến thức làm việc về ngôn ngữ lập trình C#
- Thư viện Aspose.Words cho .NET được cài đặt trong dự án của bạn
- Một tài liệu Word chứa các hiệu ứng văn bản DrawML

## Bước 1: Xác định thư mục tài liệu
 Trước tiên, bạn cần đặt đường dẫn thư mục đến vị trí tài liệu Word của mình. Thay thế`"YOUR DOCUMENT DIRECTORY"` trong mã với đường dẫn thích hợp.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu và kiểm tra hiệu ứng văn bản
Tiếp theo, chúng ta sẽ tải tài liệu Word và truy cập vào tập hợp các dòng (chuỗi ký tự) trong đoạn đầu tiên của nội dung tài liệu. Tiếp theo, chúng tôi sẽ kiểm tra xem có bất kỳ hiệu ứng văn bản DrawML cụ thể nào được áp dụng cho phông chữ của lần chạy đầu tiên hay không.

```csharp
// Tải tài liệu
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Kiểm tra hiệu ứng văn bản DrawML
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Mã nguồn mẫu để kiểm tra hiệu ứng DMLText bằng Aspose.Words cho .NET 

```csharp

// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// Một lần chạy có thể áp dụng một số hiệu ứng văn bản Dml.
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã biết cách kiểm tra hiệu ứng văn bản DrawML trong tài liệu Word bằng Aspose.Words cho .NET. Kiểm tra hiệu ứng văn bản DrawML cho phép bạn xác định các phần văn bản được áp dụng các hiệu ứng cụ thể. Hãy thoải mái sử dụng tính năng này để thao tác và phân tích hiệu ứng văn bản trong tài liệu Word của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể truy cập các hiệu ứng văn bản DrawML trong tài liệu Word bằng Aspose.Words?

Trả lời: Với Aspose.Words, bạn có thể truy cập các hiệu ứng văn bản DrawML trong tài liệu Word bằng API được cung cấp. Bạn có thể duyệt các thành phần văn bản và kiểm tra các thuộc tính cụ thể của hiệu ứng văn bản, chẳng hạn như màu sắc, kích thước, v.v.

#### Hỏi: Những loại hiệu ứng văn bản DrawML nào thường được sử dụng trong tài liệu Word?

Trả lời: Các loại hiệu ứng văn bản DrawML thường được sử dụng trong tài liệu Word bao gồm bóng, phản chiếu, ánh sáng, chuyển màu, v.v. Những hiệu ứng này có thể được áp dụng để cải thiện hình thức và định dạng của văn bản.

#### Câu hỏi: Làm cách nào để kiểm tra màu của hiệu ứng văn bản DrawML trong tài liệu Word?

Trả lời: Để kiểm tra màu của hiệu ứng văn bản DrawML trong tài liệu Word, bạn có thể sử dụng các phương thức do Aspose.Words cung cấp để truy cập các thuộc tính màu của hiệu ứng văn bản. Bằng cách này, bạn có thể lấy màu được sử dụng cho hiệu ứng văn bản cụ thể.

#### Hỏi: Có thể kiểm tra hiệu ứng văn bản trong tài liệu Word có nhiều phần không?

Trả lời: Có, Aspose.Words cho phép kiểm tra hiệu ứng văn bản trong tài liệu Word có chứa nhiều phần. Bạn có thể điều hướng qua từng phần của tài liệu và truy cập các hiệu ứng văn bản cho từng phần riêng lẻ.

#### Hỏi: Làm cách nào tôi có thể kiểm tra độ mờ của hiệu ứng văn bản DrawML trong tài liệu Word?

Trả lời: Để kiểm tra độ mờ của hiệu ứng văn bản DrawML trong tài liệu Word, bạn có thể sử dụng các phương thức do Aspose.Words cung cấp để truy cập các thuộc tính độ mờ của hiệu ứng văn bản. Điều này sẽ cho phép bạn áp dụng giá trị độ mờ cho hiệu ứng văn bản cụ thể.