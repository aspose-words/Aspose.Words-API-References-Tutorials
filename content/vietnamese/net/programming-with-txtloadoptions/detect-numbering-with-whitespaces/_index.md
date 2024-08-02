---
title: Phát hiện đánh số bằng khoảng trắng
linktitle: Phát hiện đánh số bằng khoảng trắng
second_title: API xử lý tài liệu Aspose.Words
description: Khám phá cách sử dụng Aspose.Words cho .NET để phát hiện việc đánh số có khoảng trắng trong tài liệu văn bản gốc và đảm bảo danh sách của bạn được nhận dạng chính xác.
type: docs
weight: 10
url: /vi/net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
## Giới thiệu

Aspose.Words dành cho những người đam mê .NET! Hôm nay, chúng ta sẽ đi sâu vào một tính năng thú vị có thể giúp việc xử lý danh sách trong tài liệu văn bản gốc trở nên dễ dàng. Bạn đã bao giờ xử lý các tệp văn bản trong đó một số dòng được coi là danh sách nhưng chúng trông không ổn lắm khi được tải vào tài liệu Word? Chà, chúng ta có một mẹo nhỏ: phát hiện việc đánh số bằng khoảng trắng. Hướng dẫn này sẽ hướng dẫn bạn cách sử dụng`DetectNumberingWithWhitespaces` tùy chọn trong Aspose.Words for .NET để đảm bảo danh sách của bạn được nhận dạng chính xác, ngay cả khi có khoảng trắng giữa các số và văn bản.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

-  Aspose.Words for .NET: Bạn có thể tải xuống từ[Giả định phát hành](https://releases.aspose.com/words/net/) trang.
- Môi trường phát triển: Visual Studio hoặc bất kỳ IDE C# nào khác.
- .NET Framework được cài đặt trên máy của bạn.
- Kiến thức cơ bản về C#: Hiểu những điều cơ bản sẽ giúp bạn theo dõi các ví dụ.

## Nhập không gian tên

Trước khi chuyển sang mã, hãy đảm bảo bạn đã nhập các không gian tên cần thiết vào dự án của mình. Đây là một đoạn ngắn để giúp bạn bắt đầu:

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Loading;
```

Hãy chia nhỏ quy trình thành các bước đơn giản, dễ quản lý. Mỗi bước sẽ hướng dẫn bạn mã cần thiết và giải thích điều gì đang xảy ra.

## Bước 1: Xác định thư mục tài liệu của bạn

Trước tiên, hãy thiết lập đường dẫn đến thư mục tài liệu của bạn. Đây là nơi các tập tin đầu vào và đầu ra của bạn sẽ được lưu trữ.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo tài liệu văn bản gốc

Tiếp theo, chúng ta sẽ tạo một tài liệu văn bản gốc dưới dạng một chuỗi. Tài liệu này sẽ chứa các phần có thể được hiểu là danh sách.

```csharp
const string textDoc = "Full stop delimiters:\n" +
                       "1. First list item 1\n" +
                       "2. First list item 2\n" +
                       "3. First list item 3\n\n" +
                       "Right bracket delimiters:\n" +
                       "1) Second list item 1\n" +
                       "2) Second list item 2\n" +
                       "3) Second list item 3\n\n" +
                       "Bullet delimiters:\n" +
                       "• Third list item 1\n" +
                       "• Third list item 2\n" +
                       "• Third list item 3\n\n" +
                       "Whitespace delimiters:\n" +
                       "1 Fourth list item 1\n" +
                       "2 Fourth list item 2\n" +
                       "3 Fourth list item 3";
```

## Bước 3: Cấu hình LoadOptions

 Để phát hiện việc đánh số có khoảng trắng, chúng ta cần đặt`DetectNumberingWithWhitespaces` tùy chọn để`true` trong một`TxtLoadOptions` sự vật.

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

## Bước 4: Tải tài liệu

 Bây giờ, hãy tải tài liệu bằng cách sử dụng`TxtLoadOptions` như một tham số. Điều này đảm bảo rằng danh sách thứ tư (có khoảng trắng) được phát hiện chính xác.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu vào thư mục được chỉ định của bạn. Điều này sẽ xuất ra một tài liệu Word với danh sách được phát hiện chính xác.

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

## Phần kết luận

Và bạn có nó rồi đấy! Chỉ với một vài dòng mã, bạn đã thành thạo nghệ thuật phát hiện việc đánh số bằng khoảng trắng trong tài liệu văn bản gốc bằng cách sử dụng Aspose.Words cho .NET. Tính năng này có thể cực kỳ tiện dụng khi xử lý các định dạng văn bản khác nhau và đảm bảo danh sách của bạn được thể hiện chính xác trong tài liệu Word. Vì vậy, lần tới khi gặp phải những danh sách phức tạp đó, bạn sẽ biết chính xác phải làm gì.

## Câu hỏi thường gặp

###  Là gì`DetectNumberingWithWhitespaces` in Aspose.Words for .NET?
`DetectNumberingWithWhitespaces` là một lựa chọn trong`TxtLoadOptions` điều đó cho phép Aspose.Words nhận dạng danh sách ngay cả khi có khoảng trắng giữa phần đánh số và văn bản mục danh sách.

### Tôi có thể sử dụng tính năng này cho các dấu phân cách khác như dấu đầu dòng và dấu ngoặc không?
 Có, Aspose.Words tự động phát hiện các danh sách có dấu phân cách phổ biến như dấu đầu dòng và dấu ngoặc. Các`DetectNumberingWithWhitespaces` đặc biệt trợ giúp với các danh sách có khoảng trắng.

###  Điều gì xảy ra nếu tôi không sử dụng`DetectNumberingWithWhitespaces`?
Nếu không có tùy chọn này, các danh sách có khoảng trắng giữa phần đánh số và văn bản có thể không được nhận dạng là danh sách và các mục có thể xuất hiện dưới dạng đoạn văn đơn giản.

### Tính năng này có sẵn trong các sản phẩm Aspose khác không?
Tính năng cụ thể này được thiết kế riêng cho Aspose.Words for .NET, được thiết kế để xử lý việc xử lý tài liệu Word.

### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Words cho .NET?
 Bạn có thể xin giấy phép tạm thời từ[Cung cấp giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) trang.

