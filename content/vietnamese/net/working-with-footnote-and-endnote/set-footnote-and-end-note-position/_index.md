---
title: Đặt vị trí chú thích cuối trang và chú thích cuối trang
linktitle: Đặt vị trí chú thích cuối trang và chú thích cuối trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt vị trí chú thích cuối trang và chú thích cuối trang trong tài liệu Word bằng Aspose.Words cho .NET với hướng dẫn chi tiết từng bước này.
type: docs
weight: 10
url: /vi/net/working-with-footnote-and-endnote/set-footnote-and-end-note-position/
---
## Giới thiệu

Nếu bạn đang làm việc với tài liệu Word và cần quản lý chú thích cuối trang và chú thích cuối trang một cách hiệu quả thì Aspose.Words for .NET là thư viện bạn nên sử dụng. Hướng dẫn này sẽ hướng dẫn bạn cách đặt vị trí chú thích cuối trang và chú thích cuối trang trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ chia nhỏ từng bước để bạn dễ dàng theo dõi và thực hiện.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có những điều sau:

-  Thư viện Aspose.Words for .NET: Bạn có thể tải xuống từ[đây](https://releases.aspose.com/words/net/).
- Visual Studio: Mọi phiên bản gần đây đều hoạt động tốt.
- Kiến thức cơ bản về C#: Hiểu những điều cơ bản sẽ giúp bạn dễ dàng theo dõi.

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cần thiết trong dự án C# của bạn:

```csharp
using System;
using Aspose.Words;
```

## Bước 1: Tải tài liệu Word

Để bắt đầu, bạn cần tải tài liệu Word của mình vào đối tượng Aspose.Words Document. Điều này sẽ cho phép bạn thao tác nội dung của tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 Trong mã này, thay thế`"YOUR DOCUMENT DIRECTORY"`với đường dẫn thực tế nơi tài liệu của bạn được đặt.

## Bước 2: Đặt vị trí chú thích cuối trang

Tiếp theo, bạn sẽ thiết lập vị trí của chú thích cuối trang. Aspose.Words for .NET cho phép bạn đặt chú thích cuối trang ở cuối trang hoặc bên dưới văn bản.

```csharp
doc.FootnoteOptions.Position = FootnotePosition.BeneathText;
```

 Ở đây, chúng tôi đã đặt chú thích cuối trang xuất hiện bên dưới văn bản. Nếu bạn thích chúng ở cuối trang, hãy sử dụng`FootnotePosition.BottomOfPage`.

## Bước 3: Đặt vị trí chú thích cuối

Tương tự, bạn có thể đặt vị trí của chú thích cuối. Chú thích cuối có thể được đặt ở cuối phần hoặc ở cuối tài liệu.

```csharp
doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;
```

 Trong ví dụ này, chú thích cuối được đặt ở cuối mỗi phần. Để đặt chúng ở cuối tài liệu, hãy sử dụng`EndnotePosition.EndOfDocument`.

## Bước 4: Lưu tài liệu

Cuối cùng, lưu tài liệu để áp dụng các thay đổi. Đảm bảo bạn chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetFootnoteAndEndNotePosition.docx");
```

Dòng này lưu tài liệu đã sửa đổi vào thư mục được chỉ định của bạn.

## Phần kết luận

Việc đặt vị trí chú thích cuối trang và chú thích cuối trang trong tài liệu Word bằng Aspose.Words cho .NET thật đơn giản khi bạn biết các bước. Bằng cách làm theo hướng dẫn này, bạn có thể tùy chỉnh tài liệu cho phù hợp với nhu cầu của mình, đảm bảo rằng chú thích cuối trang và chú thích cuối được đặt chính xác ở nơi bạn muốn.

## Câu hỏi thường gặp

### Tôi có thể đặt các vị trí khác nhau cho từng chú thích cuối trang hoặc chú thích cuối sách không?

Không, Aspose.Words for .NET đặt vị trí cho tất cả chú thích cuối trang và chú thích cuối trong tài liệu một cách thống nhất.

### Aspose.Words for .NET có tương thích với tất cả các phiên bản của tài liệu Word không?

Có, Aspose.Words for .NET hỗ trợ nhiều định dạng tài liệu Word, bao gồm DOC, DOCX, RTF, v.v.

### Tôi có thể sử dụng Aspose.Words cho .NET với các ngôn ngữ lập trình khác không?

Aspose.Words for .NET được thiết kế cho các ứng dụng .NET, nhưng bạn có thể sử dụng nó với bất kỳ ngôn ngữ nào được .NET hỗ trợ như C#, VB.NET, v.v.

### Có bản dùng thử miễn phí dành cho Aspose.Words cho .NET không?

 Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu chi tiết hơn về Aspose.Words cho .NET ở đâu?

 Tài liệu chi tiết có sẵn[đây](https://reference.aspose.com/words/net/).