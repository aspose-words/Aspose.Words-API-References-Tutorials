---
title: Trường Chèn Bao gồm Văn bản Không có Trình tạo Tài liệu
linktitle: Chèn FieldIncludeText mà không cần Trình tạo tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn trường FieldIncludeText vào tài liệu Word của bạn bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng chức năng "Chèn trường FieldIncludeText" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã được cung cấp, bạn phải chỉ định thư mục tài liệu của mình. Thay thế giá trị "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo tài liệu và đoạn văn

Chúng tôi bắt đầu bằng cách tạo một tài liệu mới và khởi tạo một đoạn văn.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Bước 3: Chèn trường FieldIncludeText

 Chúng tôi sử dụng`AppendField()` phương pháp chèn trường FieldIncludeText vào đoạn văn.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Sau đó, chúng tôi định cấu hình các thuộc tính của trường FieldIncludeText bằng cách chỉ định tên của dấu trang và tên của tệp nguồn.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Tiếp theo, chúng ta thêm đoạn văn vào phần nội dung của tài liệu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Cuối cùng, chúng tôi gọi`Update()` phương pháp cập nhật trường.

```csharp
fieldIncludeText.Update();
```

### Ví dụ về mã nguồn để chèn trường FieldIncludeText bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và đoạn văn.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Chèn trường FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

Trong ví dụ này, chúng tôi đã tạo một tài liệu mới, khởi tạo một đoạn văn, chèn FieldIncludeTexten chỉ định tên dấu trang và tên tệp nguồn, đồng thời lưu tài liệu bằng tên tệp được chỉ định.

Phần này kết thúc hướng dẫn của chúng tôi về cách sử dụng tính năng "Chèn FieldIncludeText" với Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể chỉ định tệp nguồn cho trường bao gồm văn bản trong Aspose.Words cho .NET?

 Trả lời: Để chỉ định tệp nguồn cho trường bao gồm văn bản trong Aspose.Words cho .NET, bạn có thể sử dụng`FieldIncludeText.SourceFullName`thuộc tính để đặt đường dẫn đầy đủ của tệp nguồn. Đảm bảo tệp nguồn có thể truy cập được và chứa nội dung bạn muốn đưa vào trường đưa văn bản vào.

#### Câu hỏi: Tôi có thể đưa văn bản từ macro vào trường bao gồm văn bản bằng Aspose.Words cho .NET không?

 Trả lời: Có, bạn có thể đưa văn bản từ macro vào trường bao gồm văn bản bằng Aspose.Words for .NET. Bạn có thể dùng`FieldIncludeText.IncludeText` thuộc tính để chỉ định tên của macro có nội dung sẽ được đưa vào trường.

#### Câu hỏi: Việc chèn trường bao gồm văn bản mà không có trình tạo tài liệu có ảnh hưởng đến cấu trúc tài liệu Word với Aspose.Words cho .NET không?

Đáp: Việc chèn trường bao gồm văn bản mà không có trình tạo tài liệu sẽ không ảnh hưởng trực tiếp đến cấu trúc của tài liệu Word. Tuy nhiên, nó thêm một phần tử trường mới vào nội dung tài liệu. Bạn có thể thao tác cấu trúc tài liệu bằng cách thêm, xóa hoặc sửa đổi các thành phần hiện có theo nhu cầu của mình.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của trường bao gồm văn bản trong tài liệu Word bằng Aspose.Words cho .NET không?

Trả lời: Trường bao gồm văn bản không trực tiếp tùy chỉnh hình thức của nó trong tài liệu Word. Tuy nhiên, bạn có thể định dạng văn bản được bao gồm bằng cách sử dụng thuộc tính đoạn văn, thuộc tính phông chữ và các đối tượng định dạng khác có sẵn trong Aspose.Words for .NET.