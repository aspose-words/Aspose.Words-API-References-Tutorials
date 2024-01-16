---
title: Chèn trường tác giả
linktitle: Chèn trường tác giả
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách Chèn trường TÁC GIẢ vào tài liệu Word của bạn bằng Aspose.Words cho .NET. Chỉ định tên tác giả để cá nhân hóa tài liệu của bạn.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-author-field/
---


Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng tính năng "Chèn trường AUTHOR" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã được cung cấp, bạn phải chỉ định thư mục tài liệu của mình. Thay thế giá trị "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo tài liệu và đoạn văn

Chúng tôi bắt đầu bằng cách tạo một tài liệu mới và tìm nạp đoạn đầu tiên.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Bước 3: Chèn trường AUTHOR

 Chúng tôi sử dụng`AppendField()` phương pháp chèn trường AUTHOR vào đoạn văn.

```csharp
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);
```

 Sau đó chúng tôi định cấu hình trường`AuthorName` thuộc tính để chỉ định tên tác giả.

```csharp
field. AuthorName = "Test1";
```

 Cuối cùng, chúng tôi gọi`Update()` phương pháp cập nhật trường.

```csharp
field. Update();
```

### Ví dụ về mã nguồn để chèn trường AUTHOR với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Chèn trường TÁC GIẢ.
FieldAuthor field = (FieldAuthor)para.AppendField(FieldType.FieldAuthor, false);

field. AuthorName = "Test1";

field. Update();

doc.Save(dataDir + "InsertionAuthorField.docx");
```

Trong ví dụ này, chúng tôi đã tạo một tài liệu mới, chèn trường TÁC GIẢ, đặt cấu hình tên tác giả và lưu tài liệu với tên tệp được chỉ định.

Phần này kết thúc hướng dẫn của chúng tôi về cách sử dụng tính năng "Chèn trường AUTHOR" với Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Trường tác giả trong Aspose.Words là gì?

Trả lời: Trường tác giả trong Aspose.Words là trường đặc biệt tự động chèn và cập nhật tên tác giả trong tài liệu Word. Nó thường được sử dụng để chỉ ra ai đã tạo hoặc sửa đổi tài liệu.

#### Hỏi: Làm cách nào để cập nhật trường tác giả trong tài liệu Word bằng Aspose.Words?

Đáp: Trường tác giả trong tài liệu Word có thể được cập nhật để phản ánh tên tác giả hiện tại. Để làm điều này, bạn có thể sử dụng phương thức UpdateFields có sẵn trong lớp Document. Phương pháp này sẽ cập nhật tất cả các trường trong tài liệu, bao gồm cả trường tác giả.

#### Hỏi: Có thể tùy chỉnh định dạng của trường tác giả trong tài liệu Word không?

Trả lời: Có, có thể tùy chỉnh định dạng của trường tác giả trong tài liệu Word. Theo mặc định, trường tác giả chỉ hiển thị tên tác giả. Tuy nhiên, bạn có thể thêm thông tin bổ sung như ngày và giờ sửa đổi bằng cách sử dụng các tùy chọn định dạng có sẵn trong Aspose.Words.

#### Hỏi: Trường tác giả có nhạy cảm với những thay đổi tiếp theo đối với tên tác giả không?

Đáp: Có, trường tác giả rất nhạy cảm với những thay đổi tiếp theo đối với tên tác giả. Nếu bạn thay đổi tên tác giả trong thuộc tính tài liệu, trường tác giả sẽ tự động cập nhật tên mới khi cập nhật các trường tài liệu.