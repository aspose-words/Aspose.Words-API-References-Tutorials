---
title: Chèn trường hợp nhất bằng DOM
linktitle: Chèn trường hợp nhất bằng DOM
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn trường hợp nhất trường tùy chỉnh vào tài liệu Word của bạn bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-merge-field-using-dom/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới sử dụng tính năng "Chèn trường hợp nhất trường" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã được cung cấp, bạn phải chỉ định thư mục tài liệu của mình. Thay thế giá trị "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo Tài liệu và DocumentBuilder

Chúng tôi bắt đầu bằng cách tạo một tài liệu mới và khởi tạo DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Di chuyển con trỏ đến đoạn văn

 Chúng tôi sử dụng`MoveTo()` phương thức của DocumentBuilder để di chuyển con trỏ đến đoạn văn mà chúng ta muốn chèn trường hợp nhất trường.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Bước 4: Chèn trường phối trường

 Chúng tôi sử dụng DocumentBuilder's`InsertField()` phương pháp chèn trường hợp nhất trường vào đoạn văn.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Sau đó, chúng tôi đặt cấu hình thuộc tính trường phối trường bằng cách chỉ định các tùy chọn thích hợp, chẳng hạn như tên trường, văn bản trước và sau trường cũng như các tùy chọn định dạng dọc.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Cuối cùng, chúng tôi gọi`Update()` phương pháp cập nhật trường.

```csharp
field. Update();
```

### Mã nguồn mẫu để chèn trường hợp nhất trường với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Di chuyển con trỏ tới đoạn văn.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Chèn trường hợp nhất trường.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Cập nhật trường.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

Trong ví dụ này, chúng tôi đã tạo một tài liệu mới, di chuyển con trỏ đến đoạn văn mong muốn rồi chèn trường phối trường vào tài liệu.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể chèn trường hợp nhất vào tài liệu Word bằng Aspose.Words cho .NET với DOM?

Trả lời: Để chèn trường hợp nhất vào tài liệu Word bằng Aspose.Words cho .NET với DOM, bạn có thể làm theo các bước sau:

1. Dẫn hướng đến đoạn mà bạn muốn chèn trường phối.
2.  Tạo một`FieldMergeField` sự vật.
3. Đặt các thuộc tính trường phối, chẳng hạn như tên trường và các tùy chọn định dạng.
4.  Thêm trường hợp nhất vào đoạn văn bằng cách sử dụng`Paragraph.AppendChild` phương pháp.

#### Câu hỏi: Làm cách nào tôi có thể chỉ định dữ liệu nguồn cho trường hợp nhất trong Aspose.Words cho .NET?

Trả lời: Để chỉ định dữ liệu nguồn cho trường hợp nhất trong Aspose.Words cho .NET, bạn có thể sử dụng`FieldMergeField.FieldName` phương pháp đặt tên trường hợp nhất, là tên của trường trong nguồn dữ liệu bên ngoài, chẳng hạn như tệp CSV, cơ sở dữ liệu, v.v. Bạn cũng có thể sử dụng phương thức`FieldMergeField.Text` phương pháp để đặt trực tiếp giá trị trường hợp nhất.

#### Câu hỏi: Tôi có thể tùy chỉnh giao diện của trường phối trong tài liệu Word bằng Aspose.Words cho .NET không?

 Trả lời: Có, bạn có thể tùy chỉnh giao diện của trường hợp nhất trong tài liệu Word bằng Aspose.Words for .NET. Bạn có thể đặt các tùy chọn định dạng như kiểu chữ, phông chữ, màu sắc, v.v. bằng cách sử dụng các thuộc tính của`FieldMergeField` sự vật.

#### Câu hỏi: Làm cách nào để kiểm tra xem trường hợp nhất đã được chèn thành công vào tài liệu Word bằng Aspose.Words cho .NET hay chưa?

 Đáp: Để kiểm tra xem trường hợp nhất đã được chèn thành công hay chưa, bạn có thể duyệt nội dung tài liệu và tìm kiếm các trường hợp hợp nhất. Bạn có thể sử dụng các phương thức và thuộc tính của`Document` đối tượng để truy cập các đoạn văn, trường và các thành phần khác của tài liệu.

#### Câu hỏi: Việc chèn trường hợp nhất bằng DOM có ảnh hưởng đến cấu trúc tài liệu Word với Aspose.Words cho .NET không?

Trả lời: Việc chèn trường hợp nhất bằng DOM không ảnh hưởng trực tiếp đến cấu trúc của tài liệu Word. Tuy nhiên, nó thêm một phần tử trường mới vào nội dung tài liệu. Bạn có thể thao tác cấu trúc tài liệu bằng cách thêm, xóa hoặc sửa đổi các thành phần hiện có theo nhu cầu của mình.