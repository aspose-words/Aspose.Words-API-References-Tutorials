---
title: Chèn trường bằng cách sử dụng Trình tạo trường
linktitle: Chèn trường bằng cách sử dụng Trình tạo trường
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách Chèn trường tùy chỉnh vào tài liệu Word của bạn bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-field-using-field-builder/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng tính năng "Chèn trường bằng FieldBuilder" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã được cung cấp, bạn phải chỉ định thư mục tài liệu của mình. Thay thế giá trị "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tạo tài liệu

Chúng tôi bắt đầu bằng cách tạo một tài liệu mới.

```csharp
Document doc = new Document();
```

## Bước 3: Xây dựng trường IF bằng FieldBuilder

Chúng tôi sử dụng lớp FieldBuilder để xây dựng trường IF với hai trường MERGEFIELD lồng nhau. Trong ví dụ này, trường IF hiển thị họ và tên dựa trên một điều kiện.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Bước 4: Chèn trường IF vào tài liệu

 Chúng tôi sử dụng`BuildAndInsert()` phương pháp xây dựng và chèn trường IF vào một vị trí cụ thể trong tài liệu.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Mã nguồn ví dụ để chèn trường bằng FieldBuilder với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu.
Document doc = new Document();

// Xây dựng trường IF bằng FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Chèn trường IF vào tài liệu.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

Trong ví dụ này, chúng tôi đã tạo một tài liệu mới, xây dựng trường IF với các trường MERGEFIELD lồng nhau, sau đó chèn trường đó vào tài liệu tại một vị trí được chỉ định. Tài liệu sau đó được lưu với một tên tệp cụ thể.

### Câu hỏi thường gặp

#### Câu hỏi: Trình tạo trường trong Aspose.Words là gì?

Trả lời: Trình tạo trường trong Aspose.Words là một công cụ mạnh mẽ để tạo và thao tác các trường trong tài liệu Word. Nó cung cấp các tính năng nâng cao để xây dựng và tùy chỉnh các trường, bao gồm chèn mã trường và quản lý các tùy chọn định dạng.

#### Câu hỏi: Những loại trường nào có thể được chèn bằng trình tạo trường?

Trả lời: Trình tạo trường trong Aspose.Words cho phép bạn chèn các loại trường khác nhau vào tài liệu Word. Dưới đây là một số ví dụ về các loại trường thường được sử dụng:

- MERGEFIELD: dùng để hợp nhất dữ liệu từ các nguồn bên ngoài.
- NGÀY: hiển thị ngày hiện tại.
- TRANG: hiển thị số trang hiện tại.
- IF: cho phép điều kiện hiển thị nội dung theo một điều kiện.
- TOC: tự động tạo mục lục dựa trên kiểu tiêu đề tài liệu.

#### Câu hỏi: Làm cách nào để tùy chỉnh các trường được chèn bằng trình tạo trường?

Đáp: Trình tạo trường cung cấp các tùy chọn tùy chỉnh cho các trường được chèn. Bạn có thể sử dụng các phương thức và thuộc tính của hàm tạo trường để đặt các tùy chọn như định dạng trường, đối số, khóa chuyển và giá trị mặc định. Ví dụ: bạn có thể đặt định dạng ngày, định dạng số, dấu phân cách hàng nghìn, v.v.
  