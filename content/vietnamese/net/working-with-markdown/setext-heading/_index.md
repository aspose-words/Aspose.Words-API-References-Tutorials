---
title: Tiêu đề Setex
linktitle: Tiêu đề Setex
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng tiêu đề Setext để định dạng tài liệu của bạn với hướng dẫn từng bước Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-markdown/setext-heading/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách sử dụng tính năng Setext Heading với Aspose.Words cho .NET. Tiêu đề Setext là một phương pháp định dạng tiêu đề thay thế trong tài liệu Markdown.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Bước 2: Sử dụng kiểu tiêu đề Setext

Chúng tôi sẽ sử dụng kiểu đoạn văn "Tiêu đề 1" mặc định để tạo tiêu đề cấp 1 trong tài liệu của mình.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Bước 3: Đặt lại kiểu

Chúng tôi đặt lại các kiểu phông chữ đã áp dụng trước đó để tránh mọi sự kết hợp kiểu không mong muốn giữa các đoạn văn.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Bước 4: Tùy chỉnh cấp độ tiêu đề Setext

Chúng ta có thể tùy chỉnh các cấp độ tiêu đề Setext bằng cách thêm các kiểu đoạn văn mới dựa trên các kiểu tiêu đề hiện có. Trong ví dụ này, chúng tôi đang tạo kiểu "SetextHeading1" dựa trên kiểu "Tiêu đề 1" để thể hiện tiêu đề cấp 1 ở định dạng Setext.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Bước 5: Lưu tài liệu

Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng mong muốn.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Mã nguồn ví dụ cho tiêu đề Setext với Aspose.Words for .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Đặt lại kiểu từ đoạn trước để không kết hợp kiểu giữa các đoạn.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Đặt lại kiểu từ đoạn trước để không kết hợp kiểu giữa các đoạn.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Cấp tiêu đề Setex sẽ được đặt lại thành 2 nếu đoạn văn cơ sở có cấp Tiêu đề lớn hơn 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### Câu hỏi thường gặp

#### Câu hỏi: Tiêu đề Setext Markdown là gì?

Đáp: Tiêu đề Setext Markdown là một cách khác để tạo tiêu đề trong tài liệu Markdown. Nó sử dụng các ký tự gạch dưới (= hoặc -) để biểu thị các cấp độ khác nhau của tiêu đề.

#### Câu hỏi: Làm cách nào để sử dụng tiêu đề Setext Markdown?

Đáp: Để sử dụng tiêu đề Setext Markdown, hãy đặt dấu gạch dưới bên dưới văn bản tiêu đề. Sử dụng dấu bằng (=) cho tiêu đề cấp 1 và dấu gạch nối (-) cho tiêu đề cấp 2.

#### Câu hỏi: Có bất kỳ hạn chế nào khi sử dụng tiêu đề Setext Markdown không?

Đáp: Các tiêu đề Setext Markdown có những hạn chế về mặt phân cấp tiêu đề và không khác biệt về mặt trực quan như các tiêu đề Markdown tiêu chuẩn.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của tiêu đề Setext Markdown không?

Trả lời: Trong Markdown tiêu chuẩn, không thể tùy chỉnh giao diện của tiêu đề Setext Markdown. Chúng có giao diện được xác định trước dựa trên các ký tự gạch dưới được sử dụng.

#### Câu hỏi: Tất cả các trình soạn thảo Markdown có hỗ trợ các tiêu đề Setext Markdown không?

Trả lời: Hỗ trợ cho tiêu đề Setext Markdown có thể khác nhau giữa các trình soạn thảo Markdown. Kiểm tra tài liệu cụ thể của nhà xuất bản của bạn để chắc chắn.