---
title: Đặt vị trí chú thích cuối trang và chú thích cuối trang
linktitle: Đặt vị trí chú thích cuối trang và chú thích cuối trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt vị trí của chú thích cuối trang và chú thích cuối trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng Aspose.Words cho .NET để đặt vị trí của chú thích cuối trang và chú thích cuối trong tài liệu Word. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa làm như vậy, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Khởi tạo đối tượng tài liệu

 Đầu tiên, khởi tạo`Document` đối tượng bằng cách cung cấp đường dẫn đến tài liệu nguồn của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");
```

## Bước 2: Đặt vị trí chú thích cuối trang và chú thích cuối trang

 Tiếp theo, truy cập vào`FootnoteOptions` Và`EndnoteOptions`thuộc tính của tài liệu để đặt vị trí của chú thích cuối trang và chú thích cuối trang. Trong ví dụ này, chúng tôi đặt vị trí của chú thích ở bên dưới văn bản và vị trí của chú thích ở cuối phần:

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

## Bước 3: Lưu tài liệu

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Đó là nó! Bạn đã đặt thành công vị trí của chú thích cuối trang và chú thích cuối trong tài liệu Word bằng Aspose.Words for .NET.

### Mã nguồn ví dụ cho Đặt vị trí chú thích cuối trang và chú thích cuối trang bằng Aspose.Words cho .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";     
Document doc = new Document(dataDir + "Document.docx");

doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó theo yêu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể định vị chú thích cuối trang và chú thích cuối trong Aspose.Words?

 Đáp: Để định vị chú thích cuối trang và chú thích cuối trong Aspose.Words, bạn cần sử dụng`FootnoteOptions` lớp học và`Position` tài sản. Bạn có thể đặt thuộc tính này thành bất kỳ giá trị nào bạn muốn, chẳng hạn như`BottomOfPage` (ở cuối trang) hoặc`EndOfSection` (ở cuối phần).

#### Hỏi: Có thể tùy chỉnh vị trí của chú thích cuối trang và chú thích cuối cho từng trang hoặc phần của tài liệu không?

Trả lời: Có, có thể tùy chỉnh vị trí của chú thích cuối trang và chú thích cuối cho từng trang hoặc phần của tài liệu. Bạn có thể sử dụng các phương pháp thao tác trang và phần Aspose.Words để xác định các vị trí cụ thể cho chú thích cuối trang và chú thích cuối trang.

#### Hỏi: Làm cách nào để xóa chú thích cuối trang hoặc chú thích cuối khỏi tài liệu?

 Trả lời: Để xóa chú thích cuối trang hoặc chú thích cuối khỏi tài liệu trong Aspose.Words, bạn có thể sử dụng các phương pháp thích hợp như`RemoveAllFootnotes` để loại bỏ tất cả các chú thích cuối trang hoặc`RemoveAllEndnotes` để loại bỏ tất cả các chú thích cuối. Hãy nhớ lưu tài liệu sau khi thực hiện các thao tác này.

#### Hỏi: Chú thích cuối trang và chú thích cuối có thể được đặt bên ngoài lề trang không?

Không, theo mặc định, chú thích cuối trang và chú thích cuối không thể được đặt bên ngoài lề trang trong Aspose.Words. Tuy nhiên, bạn có thể điều chỉnh lề tài liệu để có thêm khoảng trống cho chú thích cuối trang và chú thích cuối nếu cần.

#### Câu hỏi: Có thể tùy chỉnh chú thích cuối trang và chú thích cuối bằng phông chữ hoặc kiểu định dạng cụ thể không?

Trả lời: Có, bạn có thể tùy chỉnh chú thích cuối trang và chú thích cuối bằng phông chữ hoặc kiểu định dạng cụ thể trong Aspose.Words. Bạn có thể sử dụng các phương thức và thuộc tính có sẵn để áp dụng kiểu phông chữ, màu sắc, cỡ chữ, v.v. cho chú thích cuối trang và chú thích cuối trang.