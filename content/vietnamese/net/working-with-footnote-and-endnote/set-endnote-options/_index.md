---
title: Đặt tùy chọn chú thích cuối
linktitle: Đặt tùy chọn chú thích cuối
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt tùy chọn chú thích cuối trong tài liệu Word bằng Aspose.Words cho .NET. Hướng dẫn từng bước với mã nguồn mẫu.
type: docs
weight: 10
url: /vi/net/working-with-footnote-and-endnote/set-endnote-options/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng Aspose.Words cho .NET để đặt các tùy chọn chú thích cuối trong tài liệu Word. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo rằng bạn đã cài đặt và thiết lập Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa làm như vậy, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Khởi tạo đối tượng tài liệu

 Đầu tiên, khởi tạo`Document` đối tượng bằng cách cung cấp đường dẫn đến tài liệu nguồn của bạn:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Bước 2: Khởi tạo đối tượng DocumentBuilder

 Tiếp theo, khởi tạo`DocumentBuilder` đối tượng thực hiện các thao tác trên tài liệu:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Thêm văn bản và chú thích

 Sử dụng`Write` phương pháp của`DocumentBuilder` đối tượng để thêm văn bản vào tài liệu và`InsertFootnote` phương pháp chèn chú thích cuối:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Bước 4: Thiết lập tùy chọn Endnote

 Truy cập`EndnoteOptions` thuộc tính của tài liệu để sửa đổi các tùy chọn chú thích cuối. Trong ví dụ này, chúng tôi đặt quy tắc khởi động lại để khởi động lại trên mỗi trang và vị trí ở cuối phần:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Đó là nó! Bạn đã đặt thành công các tùy chọn ghi chú cuối trong tài liệu Word bằng Aspose.Words cho .NET.

### Mã nguồn mẫu cho Set Endnote Options sử dụng Aspose.Words for .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó theo yêu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể tạo kiểu cho chú thích cuối trong Aspose.Words?

Đáp: Để tạo kiểu cho chú thích cuối trong Aspose.Words, bạn có thể sử dụng`EndnoteOptions` lớp học và`SeparatorNoteTextStyle` tài sản. Bạn có thể chỉ định kiểu phông chữ, kích thước, màu sắc, v.v. cho chú thích bằng thuộc tính này.

#### Hỏi: Có thể tùy chỉnh cách đánh số chú thích cuối trong tài liệu không?

 Trả lời: Có, có thể tùy chỉnh cách đánh số chú thích cuối trong tài liệu. Bạn có thể dùng`RestartRule` Và`NumberStyle` thuộc tính của`EndnoteOptions` lớp để xác định các quy tắc khởi động lại và kiểu đánh số cụ thể.

#### Câu hỏi: Làm cách nào tôi có thể định vị chú thích cuối trong tài liệu?

 Đáp: Để định vị chú thích cuối trong tài liệu, bạn có thể sử dụng`Position` tài sản của`EndnoteOptions` lớp học. Bạn có thể chỉ định nên đặt chú thích cuối ở cuối mỗi trang, ở cuối mỗi phần hay ở cuối tài liệu.

#### Hỏi: Tôi có thể tùy chỉnh định dạng đánh số chú thích cuối trang không?

 Trả lời: Có, bạn có thể tùy chỉnh định dạng đánh số chú thích cuối trong Aspose.Words. Sử dụng`NumberFormat` tài sản của`EndnoteOptions` class để đặt định dạng mong muốn, chẳng hạn như chữ số Ả Rập, chữ số La Mã, chữ cái, v.v.

#### Câu hỏi: Có thể tiếp tục đánh số chú thích cuối giữa các phần của tài liệu không?

Đáp: Có, có thể tiếp tục đánh số chú thích cuối giữa các phần của tài liệu. Sử dụng`RestartRule` tài sản của`EndnoteOptions` lớp và đặt nó thành`RestartContinuous` để cho phép đánh số tiếp tục giữa các phần.