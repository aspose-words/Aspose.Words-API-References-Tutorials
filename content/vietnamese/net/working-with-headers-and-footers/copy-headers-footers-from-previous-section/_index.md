---
title: Sao chép đầu trang chân trang từ phần trước
linktitle: Sao chép đầu trang chân trang từ phần trước
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sao chép đầu trang và chân trang từ phần trước trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sao chép đầu trang và chân trang từ phần trước trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo rằng bạn đã cài đặt và thiết lập Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa làm như vậy, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Truy cập phần trước

 Đầu tiên, truy xuất phần trước bằng cách truy cập vào`PreviousSibling` thuộc tính của phần hiện tại:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Bước 2: Kiểm tra phần trước

Tiếp theo, kiểm tra xem phần trước có tồn tại không. Nếu không có phần trước, chúng tôi chỉ cần quay lại:

```csharp
if (previousSection == null)
    return;
```

## Bước 3: Xóa và sao chép đầu trang và chân trang

Để sao chép đầu trang và chân trang từ phần trước sang phần hiện tại, chúng tôi xóa đầu trang và chân trang hiện có trong phần hiện tại, sau đó lặp qua đầu trang và chân trang của phần trước để thêm bản sao nhân bản vào phần hiện tại:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Bước 4: Lưu tài liệu

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
doc.Save("OutputDocument.docx");
```

Đó là nó! Bạn đã sao chép thành công đầu trang và chân trang từ phần trước sang phần hiện tại trong tài liệu Word bằng Aspose.Words for .NET.

### Mã nguồn ví dụ cho Sao chép đầu trang chân trang từ phần trước bằng cách sử dụng Aspose.Words cho .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó theo yêu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể sao chép đầu trang và chân trang từ phần trước vào Aspose.Words?

 Trả lời: Để sao chép đầu trang và chân trang từ phần trước vào Aspose.Words, bạn có thể sử dụng`CopyHeadersFootersFromPreviousSection()` phương pháp hiện tại`Section`sự vật. Thao tác này sẽ sao chép đầu trang và chân trang từ phần trước sang phần hiện tại.

#### Câu hỏi: Có thể chỉ sao chép đầu trang hoặc chân trang từ phần trước trong Aspose.Words không?

 Trả lời: Có, chỉ có thể sao chép đầu trang hoặc chân trang từ phần trước trong Aspose.Words. Đối với điều này, bạn có thể sử dụng`CopyHeaderFromPreviousSection()` Và`CopyFooterFromPreviousSection()` các phương pháp hiện hành`Section` đối tượng để sao chép cụ thể đầu trang hoặc chân trang từ phần trước sang phần hiện tại.

#### Câu hỏi: Việc sao chép đầu trang và chân trang từ phần trước có thay thế đầu trang và chân trang hiện có trong phần hiện tại không?

Đáp: Có, việc sao chép đầu trang và chân trang từ phần trước sẽ thay thế đầu trang và chân trang hiện có trong phần hiện tại. Nếu bạn muốn giữ lại đầu trang và chân trang hiện có và thêm chúng vào đầu trang và chân trang đã sao chép, bạn sẽ cần thực hiện thêm thao tác để hợp nhất nội dung.

#### Câu hỏi: Làm cách nào để kiểm tra xem một phần có đầu trang hoặc chân trang từ phần trước đó trong Aspose.Words không?

Trả lời: Để kiểm tra xem một phần có đầu trang hoặc chân trang từ phần trước trong Aspose.Words hay không, bạn có thể sử dụng`HasHeader` Và`HasFooter` các thuộc tính trên`Section` đối tượng để xác định xem đầu trang hoặc chân trang có hiện diện hay không. Nếu như`HasHeader` hoặc`HasFooter` trả lại`false`, điều đó có nghĩa là không có đầu trang hoặc chân trang từ phần trước trong phần này.