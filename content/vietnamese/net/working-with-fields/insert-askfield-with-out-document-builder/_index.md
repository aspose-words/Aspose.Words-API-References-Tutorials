---
title: Chèn ASKField mà không cần Trình tạo tài liệu
linktitle: Chèn ASKField mà không cần Trình tạo tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn trường ASK vào tài liệu Word của bạn bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng tính năng "Chèn trường ASK không có DocumentBuilder" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

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

## Bước 3: Chèn trường ASK

 Chúng tôi sử dụng`AppendField()` phương pháp chèn trường ASK vào đoạn văn.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Sau đó, chúng tôi định cấu hình các thuộc tính khác nhau của trường ASK bằng cách chỉ định các giá trị mong muốn.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Cuối cùng, chúng tôi gọi`Update()` phương pháp cập nhật trường.

```csharp
field. Update();
```

### Ví dụ về mã nguồn để chèn trường ASK không có DocumentBuilder với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Chèn trường ASK.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

Trong ví dụ này, chúng tôi đã tạo một tài liệu mới, chèn trường ASK mà không sử dụng DocumentBuilder, định cấu hình các thuộc tính khác nhau của trường và lưu tài liệu với tên tệp được chỉ định.

Phần này kết thúc hướng dẫn của chúng tôi về cách sử dụng tính năng "Chèn trường ASK không có DocumentBuilder" với Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Trường ASK trong Aspose.Words là gì?

Trả lời: Trường ASK trong Aspose.Words được sử dụng để hỏi người dùng một câu hỏi khi mở tài liệu. Nó thường được sử dụng để yêu cầu thông tin hoặc phản hồi cụ thể có thể khác nhau tùy theo từng người dùng.

#### Hỏi: Làm cách nào để chèn trường ASK trong tài liệu Word mà không cần sử dụng Trình tạo tài liệu trong Aspose.Words?

Trả lời: Để chèn trường ASK trong tài liệu Word mà không sử dụng Trình tạo tài liệu trong Aspose.Words, bạn có thể làm theo các bước sau:

1. Nhập lớp Tài liệu và Trường từ không gian tên Aspose.Words.Fields.
2. Tạo một phiên bản Tài liệu bằng cách tải tài liệu hiện có của bạn.
3. Sử dụng phương thức InsertField để chèn trường ASK bằng cách chỉ định tên câu hỏi.
4. Lưu tài liệu.

#### Câu hỏi: Làm cách nào để nhận được phản hồi của người dùng cho trường ASK trong tài liệu Word?

Đáp: Để nhận phản hồi của người dùng cho trường ASK trong tài liệu Word, bạn có thể sử dụng phương thức GetFieldNames có sẵn trong lớp Tài liệu. Phương thức này trả về danh sách tên của các trường có trong tài liệu. Sau đó, bạn có thể kiểm tra xem tên trường ASK có trong danh sách hay không và truy xuất phản hồi liên quan.

#### Câu hỏi: Trường ASK có thể được sử dụng để yêu cầu thêm thông tin từ người dùng không?

Đáp: Có, trường ASK có thể được sử dụng để yêu cầu nhiều thông tin từ người dùng. Bạn có thể chèn nhiều trường ASK vào tài liệu của mình, mỗi trường có một câu hỏi khác nhau. Khi tài liệu được mở ra, người dùng sẽ được nhắc đưa ra các câu trả lời tương ứng.