---
title: Nhấn mạnh
linktitle: Nhấn mạnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng dấu nhấn mạnh (in đậm và in nghiêng) với Hướng dẫn từng bước của Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-markdown/emphases/
---

Trong ví dụ này, chúng tôi sẽ giải thích cách sử dụng dấu nhấn mạnh với Aspose.Words cho .NET. nhấn mạnh được sử dụng để nhấn mạnh các phần nhất định của văn bản, chẳng hạn như in đậm và in nghiêng.

## Bước 1: Khởi tạo tài liệu

 Đầu tiên, chúng ta sẽ khởi tạo tài liệu bằng cách tạo một thể hiện của`Document` lớp học.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Bước 2: Sử dụng trình tạo tài liệu

Tiếp theo, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Thêm văn bản bằng Emphases

Chúng ta có thể thêm văn bản nhấn mạnh bằng cách thay đổi thuộc tính phông chữ của trình tạo tài liệu. Trong ví dụ này, chúng tôi sử dụng chữ in đậm và in nghiêng để nhấn mạnh các phần khác nhau của văn bản.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Bước 4: Lưu tài liệu

 Cuối cùng, chúng ta có thể lưu tài liệu ở định dạng mong muốn. Trong ví dụ này, chúng tôi đang sử dụng`.md` tiện ích mở rộng cho định dạng Markdown.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Xin chúc mừng! Bây giờ bạn đã học cách sử dụng dấu nhấn mạnh với Aspose.Words cho .NET.

### Mã nguồn ví dụ cho Nhấn mạnh bằng Aspose.Words cho .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để đánh dấu văn bản bằng Markdown?

 Đáp: Để đánh dấu văn bản bằng Markdown, chỉ cần bao quanh văn bản bằng các ký hiệu thích hợp. Sử dụng`*` hoặc`_` cho chữ nghiêng,`**` hoặc`__` cho đậm, và`~~` để gạch ngang.

#### Hỏi: Chúng ta có thể kết hợp các điểm nổi bật khác nhau trong cùng một văn bản không?

 Đáp: Có, có thể kết hợp các điểm nổi bật khác nhau trong cùng một văn bản. Ví dụ: bạn có thể in đậm và in nghiêng một từ bằng cách sử dụng cả hai`**`Và`*` Vòng quanh thế giới.

#### Câu hỏi: Những tùy chọn đánh dấu nào có sẵn trong Markdown?

Trả lời: Các tùy chọn đánh dấu có sẵn trong Markdown là in nghiêng (`*` hoặc`_`), in đậm (`**` hoặc`__`) và gạch ngang (`~~`).

#### Câu hỏi: Làm cách nào để xử lý các trường hợp văn bản chứa các ký tự đặc biệt được Markdown sử dụng để đánh dấu?

 Trả lời: Nếu văn bản của bạn chứa các ký tự đặc biệt được Markdown sử dụng để đánh dấu, bạn có thể thoát chúng bằng cách đặt trước chúng một dấu`\` . Ví dụ,`\*` sẽ hiển thị một dấu hoa thị theo nghĩa đen.

#### Câu hỏi: Chúng tôi có thể tùy chỉnh giao diện đánh dấu bằng CSS không?

Trả lời: Việc đánh dấu trong Markdown thường được hiển thị bằng cách sử dụng các kiểu mặc định của trình duyệt. Nếu bạn chuyển đổi Markdown sang HTML, bạn có thể tùy chỉnh giao diện đánh dấu bằng cách sử dụng các quy tắc CSS.