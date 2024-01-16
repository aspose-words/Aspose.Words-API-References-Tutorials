---
title: Mã có rào chắn
linktitle: Mã có rào chắn
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng tính năng mã có rào chắn với hướng dẫn từng bước của Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-markdown/fenced-code/
---

Trong ví dụ này, chúng tôi sẽ hướng dẫn bạn cách sử dụng tính năng mã có rào chắn với Aspose.Words dành cho .NET. mã có rào chắn được sử dụng để thể hiện các khối mã có định dạng cụ thể.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Thêm kiểu cho mã có rào chắn

 Chúng tôi sẽ thêm kiểu tùy chỉnh cho mã có rào chắn bằng cách sử dụng`Styles.Add` phương pháp của`Document` sự vật. Trong ví dụ này, chúng tôi đang tạo một kiểu có tên là "FencedCode" cho mã có rào chắn.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Bước 3: Thêm mã rào chắn không có thông tin

Bây giờ chúng ta có thể thêm khối mã có rào chắn không có chuỗi thông tin bằng cách sử dụng kiểu tùy chỉnh "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Bước 4: Thêm mã rào chắn với chuỗi thông tin

Chúng ta cũng có thể thêm khối mã có hàng rào với một chuỗi thông tin bằng cách sử dụng một kiểu tùy chỉnh khác. Trong ví dụ này, chúng tôi đang tạo một kiểu có tên "FencedCode.C#" để thể hiện một khối mã C#.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Mã nguồn ví dụ cho Mã có rào chắn sử dụng Aspose.Words cho .NET

```csharp
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Câu hỏi thường gặp

#### Câu hỏi: Mã phân cách trong Markdown là gì?

Trả lời: Mã được phân tách trong Markdown là phương pháp định dạng được sử dụng để hiển thị mã trong tài liệu Markdown. Nó bao gồm việc đóng khung mã với các dấu phân cách cụ thể.

#### Câu hỏi: Lợi ích của mã phân cách trong Markdown là gì?

Trả lời: Mã được phân tách trong Markdown cải thiện khả năng đọc mã và giúp người đọc dễ hiểu hơn. Nó cũng cho phép duy trì việc đánh dấu cú pháp trong một số trình soạn thảo Markdown.

#### Câu hỏi: Sự khác biệt giữa mã được phân cách và thụt lề trong Markdown là gì?

Đáp: Mã được phân tách sử dụng các dấu phân cách cụ thể để bao quanh mã, trong khi mã thụt lề bao gồm việc thụt lề từng dòng mã bằng dấu cách hoặc tab.

#### Câu hỏi: Mã được phân tách trong Markdown có được tất cả trình soạn thảo Markdown hỗ trợ không?

Đáp: Hỗ trợ mã phân cách trong Markdown có thể khác nhau giữa các trình soạn thảo Markdown. Kiểm tra tài liệu cụ thể của nhà xuất bản của bạn để chắc chắn.

