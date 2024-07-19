---
title: Mã thụt lề
linktitle: Mã thụt lề
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng mã thụt lề với Hướng dẫn từng bước của Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-markdown/indented-code/
---

Trong ví dụ này, chúng tôi sẽ giải thích cách sử dụng tính năng mã thụt lề với Aspose.Words cho .NET. Mã thụt lề được sử dụng để thể hiện trực quan các khối mã có định dạng cụ thể.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Thêm kiểu cho mã thụt lề

 Chúng tôi sẽ thêm kiểu tùy chỉnh cho mã thụt lề bằng cách sử dụng`Styles.Add` phương pháp của`Document` sự vật. Trong ví dụ này, chúng tôi đang tạo một kiểu có tên là "IndentedCode" cho mã thụt lề.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Bước 3: Thêm mã thụt lề

Bây giờ chúng ta có thể thêm khối mã thụt lề bằng cách sử dụng kiểu tùy chỉnh "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Mã nguồn ví dụ cho mã thụt lề với Aspose.Words cho .NET

```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng tính năng mã thụt lề với Aspose.Words cho .NET.


### Câu hỏi thường gặp

#### Câu hỏi: Mã thụt lề trong Markdown là gì?

Trả lời: Mã thụt lề trong Markdown là một phương pháp định dạng được sử dụng để hiển thị mã trong tài liệu Markdown. Nó bao gồm việc thụt lề từng dòng mã bằng dấu cách hoặc tab.

#### Câu hỏi: Làm cách nào để sử dụng mã thụt lề trong Markdown?

Đáp: Để sử dụng mã thụt lề trong Markdown, hãy thụt lề từng dòng mã bằng dấu cách hoặc tab.

#### Câu hỏi: Lợi ích của mã thụt lề trong Markdown là gì?

Đáp: Mã thụt lề trong Markdown cải thiện khả năng đọc mã và giúp người đọc dễ hiểu hơn.

#### Câu hỏi: Sự khác biệt giữa mã thụt lề và khối mã trong Markdown là gì?

Đáp: Mã thụt lề được sử dụng cho các đoạn mã nhỏ được chèn vào văn bản, trong khi các khối mã được sử dụng để hiển thị các đoạn mã lớn hơn ở định dạng riêng biệt.

#### Câu hỏi: Mã thụt lề trong Markdown có được tất cả trình soạn thảo Markdown hỗ trợ không?

Đáp: Hỗ trợ mã thụt lề trong Markdown có thể khác nhau giữa các trình soạn thảo Markdown. Kiểm tra tài liệu cụ thể của nhà xuất bản của bạn để chắc chắn.