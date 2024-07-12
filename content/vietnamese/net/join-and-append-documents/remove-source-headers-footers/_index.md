---
title: Xóa chân trang đầu trang nguồn
linktitle: Xóa chân trang đầu trang nguồn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xóa đầu trang và chân trang trong tài liệu Word bằng Aspose.Words cho .NET. Đơn giản hóa việc quản lý tài liệu của bạn với hướng dẫn từng bước của chúng tôi.
type: docs
weight: 10
url: /vi/net/join-and-append-documents/remove-source-headers-footers/
---
## Giới thiệu

Trong hướng dẫn toàn diện này, chúng tôi sẽ đi sâu vào cách xóa đầu trang và chân trang khỏi tài liệu Word một cách hiệu quả bằng Aspose.Words cho .NET. Đầu trang và chân trang thường được sử dụng để đánh số trang, tiêu đề tài liệu hoặc nội dung lặp lại khác trong tài liệu Word. Cho dù bạn đang hợp nhất tài liệu hay dọn dẹp định dạng, việc nắm vững quy trình này có thể hợp lý hóa các tác vụ quản lý tài liệu của bạn. Hãy cùng khám phá quy trình từng bước để đạt được điều này bằng cách sử dụng Aspose.Words for .NET.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn đã thiết lập các điều kiện tiên quyết sau:

1. Môi trường phát triển: Đã cài đặt Visual Studio hoặc bất kỳ môi trường phát triển .NET nào khác.
2.  Aspose.Words for .NET: Đảm bảo bạn đã tải xuống và cài đặt Aspose.Words for .NET. Nếu không, bạn có thể lấy nó từ[đây](https://releases.aspose.com/words/net/).
3. Kiến thức cơ bản: Làm quen với lập trình C# và những điều cơ bản về .NET framework.

## Nhập không gian tên

Trước khi bắt đầu viết mã, hãy đảm bảo nhập các vùng tên cần thiết vào tệp C# của bạn:

```csharp
using Aspose.Words;
```

## Bước 1: Tải tài liệu nguồn

 Trước tiên, bạn cần tải tài liệu nguồn mà bạn muốn xóa đầu trang và chân trang. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế tới thư mục tài liệu của bạn, nơi chứa tài liệu nguồn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document srcDoc = new Document(dataDir + "Document source.docx");
```

## Bước 2: Tạo hoặc tải tài liệu đích

 Nếu bạn chưa tạo tài liệu đích nơi bạn muốn đặt nội dung đã sửa đổi, bạn có thể tạo một tài liệu mới`Document` đối tượng hoặc tải một đối tượng hiện có.

```csharp
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Bước 3: Xóa đầu trang và chân trang khỏi các phần

Lặp lại qua từng phần trong tài liệu nguồn (`srcDoc`) và xóa đầu trang và chân trang của nó.

```csharp
foreach (Section section in srcDoc.Sections)
{
    section.ClearHeadersFooters();
}
```

## Bước 4: Quản lý cài đặt LinkToPrevious

Để ngăn đầu trang và chân trang tiếp tục trong tài liệu đích (`dstDoc` ), đảm bảo rằng`LinkToPrevious` cài đặt cho đầu trang và chân trang được đặt thành`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Bước 5: Nối tài liệu đã sửa đổi vào tài liệu đích

Cuối cùng, nối thêm nội dung đã sửa đổi từ tài liệu nguồn (`srcDoc`) đến tài liệu đích (`dstDoc`) trong khi vẫn duy trì định dạng nguồn.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Bước 6: Lưu tài liệu kết quả

Lưu tài liệu cuối cùng đã loại bỏ đầu trang và chân trang vào thư mục đã chỉ định của bạn.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RemoveSourceHeadersFooters.docx");
```

## Phần kết luận

Xóa đầu trang và chân trang khỏi tài liệu Word bằng Aspose.Words cho .NET là một quy trình đơn giản có thể nâng cao đáng kể các tác vụ quản lý tài liệu. Bằng cách làm theo các bước được nêu ở trên, bạn có thể dọn dẹp tài liệu một cách hiệu quả để có giao diện bóng bẩy, chuyên nghiệp.

## Câu hỏi thường gặp

### Tôi có thể xóa đầu trang và chân trang khỏi các phần cụ thể không?
Có, bạn có thể lặp lại qua các phần và xóa đầu trang và chân trang một cách có chọn lọc nếu cần.

### Aspose.Words for .NET có hỗ trợ xóa đầu trang và chân trang trên nhiều tài liệu không?
Hoàn toàn có thể, bạn có thể thao tác đầu trang và chân trang trên nhiều tài liệu bằng Aspose.Words cho .NET.

###  Điều gì xảy ra nếu tôi quên đặt`LinkToPrevious` to `false`?
Đầu trang và chân trang từ tài liệu nguồn có thể tiếp tục vào tài liệu đích.

### Tôi có thể xóa đầu trang và chân trang theo chương trình mà không ảnh hưởng đến định dạng khác không?
Có, Aspose.Words for .NET cho phép bạn xóa đầu trang và chân trang trong khi vẫn giữ nguyên phần định dạng còn lại của tài liệu.

### Tôi có thể tìm thêm tài nguyên và hỗ trợ cho Aspose.Words cho .NET ở đâu?
 Tham quan[Aspose.Words cho tài liệu .NET](https://reference.aspose.com/words/net/) để biết các ví dụ và tài liệu tham khảo API chi tiết.
