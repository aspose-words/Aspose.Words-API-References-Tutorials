---
title: Trích dẫn
linktitle: Trích dẫn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng trích dẫn với Aspose.Words for .NET Hướng dẫn từng bước.
type: docs
weight: 10
url: /vi/net/working-with-markdown/quote/
---

Trong ví dụ này, chúng tôi sẽ giải thích cách sử dụng tính năng trích dẫn với Aspose. Words for .NET Quote được sử dụng để làm nổi bật các phần văn bản bằng cách bao quanh chúng bằng một đường viền đặc biệt.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Sử dụng Kiểu trích dẫn mặc định

Chúng tôi sẽ sử dụng kiểu đoạn văn mặc định có tên "Trích dẫn" để áp dụng định dạng trích dẫn cho văn bản.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Bước 3: Tạo kiểu cho các cấp độ lồng nhau

 Chúng ta có thể tạo kiểu cho các cấp độ lồng nhau bằng cách sử dụng`Styles.Add` phương pháp của`Document` sự vật. Trong ví dụ này, chúng tôi đang tạo kiểu có tên "Quote1" để thể hiện mức báo giá lồng nhau.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Mã nguồn ví dụ cho các trích dẫn với Aspose.Words cho .NET


```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

// Theo mặc định, tài liệu lưu trữ kiểu blockquote ở cấp độ đầu tiên.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Tạo kiểu cho các cấp độ lồng nhau thông qua kế thừa kiểu.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng tính năng trích dẫn với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Trích dẫn trong Markdown là gì?

Đáp: Trích dẫn trong Markdown là một cách để làm nổi bật các đoạn văn bản từ các nguồn khác hoặc tham khảo các trích dẫn nổi tiếng.

#### Câu hỏi: Làm cách nào để sử dụng dấu ngoặc kép trong Markdown?

Trả lời: Để sử dụng trích dẫn trong Markdown, hãy đặt nội dung của trích dẫn trong dấu ngoặc nhọn (`>`). Mỗi dòng trích dẫn phải bắt đầu bằng một chữ V.

#### Câu hỏi: Báo giá Markdown có hỗ trợ các thuộc tính không?

Đáp: Trích dẫn Markdown không hỗ trợ các thuộc tính cụ thể. Chúng chỉ được làm nổi bật bằng định dạng của văn bản được trích dẫn.

#### Câu hỏi: Bạn có thể nhúng dấu ngoặc kép vào Markdown không?

Trả lời: Có, có thể lồng các dấu ngoặc kép trong Markdown bằng cách thêm một mức dấu ngoặc nhọn bổ sung (`>`).