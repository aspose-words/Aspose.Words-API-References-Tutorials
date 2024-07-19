---
title: Chèn trường khối địa chỉ phối thư bằng DOM
linktitle: Chèn trường khối địa chỉ phối thư bằng DOM
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách Chèn trường khối địa chỉ trộn thư vào tài liệu Word của bạn bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, mã này sử dụng tính năng "Chèn trường khối địa chỉ phối thư" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

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

 Chúng tôi sử dụng DocumentBuilder's`MoveTo()` phương pháp di chuyển con trỏ đến đoạn mà chúng ta muốn chèn trường khối địa chỉ trộn thư.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Bước 4: Chèn trường khối địa chỉ trộn thư

 Chúng tôi sử dụng DocumentBuilder's`InsertField()` phương pháp chèn trường khối địa chỉ trộn thư vào đoạn văn.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Sau đó, chúng tôi định cấu hình các thuộc tính của trường khối địa chỉ chỉ định các tùy chọn thích hợp, chẳng hạn như bao gồm tên quốc gia/khu vực, định dạng địa chỉ theo quốc gia/khu vực, tên quốc gia/khu vực bị loại trừ, định dạng tên và địa chỉ cũng như mã nhận dạng ngôn ngữ.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Cuối cùng, chúng tôi gọi`Update()` phương pháp cập nhật trường.

```csharp
field. Update();
```

### Mã nguồn mẫu để chèn trường khối địa chỉ trộn thư với Aspose.Words cho .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Chúng tôi muốn chèn một khối địa chỉ trộn thư như thế này:
// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Kiểm tra 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// { KHÓA ĐỊA CHỈ \\c 1" }
field.IncludeCountryOrRegionName = "1";

// { KHÓA ĐỊA CHỈ \\c 1 \\d" }
field.FormatAddressOnCountryOrRegion = true;

// { ĐỊA CHỈ BLOCK \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// { ĐỊA CHỈ BLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// { ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Kiểm tra 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể tùy chỉnh định dạng của địa chỉ gửi thư trong tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Bạn có thể tùy chỉnh định dạng của địa chỉ gửi thư trong tài liệu Word bằng Aspose.Words for .NET bằng cách sử dụng các thuộc tính của`FieldAddressBlock`sự vật. Bạn có thể đặt các tùy chọn định dạng như kiểu địa chỉ, dấu phân cách, các mục tùy chọn, v.v. để có được định dạng mong muốn.

#### Câu hỏi: Làm cách nào tôi có thể chỉ định dữ liệu nguồn cho trường địa chỉ gửi thư trong Aspose.Words cho .NET?

 Trả lời: Để chỉ định dữ liệu nguồn cho trường địa chỉ gửi thư trong Aspose.Words cho .NET, bạn có thể sử dụng`FieldAddressBlock.StartAddress`Và`FieldAddressBlock.EndAddress` của cải. Các thuộc tính này được sử dụng để xác định phạm vi địa chỉ trong nguồn dữ liệu ngoài, chẳng hạn như tệp CSV, cơ sở dữ liệu, v.v.

#### Câu hỏi: Tôi có thể đưa các thành phần tùy chọn vào trường địa chỉ gửi thư bằng Aspose.Words cho .NET không?

 Trả lời: Có, bạn có thể bao gồm các thành phần tùy chọn trong trường địa chỉ gửi thư bằng Aspose.Words for .NET. Bạn có thể xác định các phần tử tùy chọn bằng cách sử dụng`FieldAddressBlock.OmitOptional` phương pháp để chỉ định có bao gồm hay loại trừ các thành phần tùy chọn như tên người nhận, tên công ty, v.v.

#### Câu hỏi: Việc chèn trường địa chỉ gửi thư bằng DOM có ảnh hưởng đến cấu trúc tài liệu Word với Aspose.Words cho .NET không?

Trả lời: Việc chèn trường địa chỉ gửi thư bằng DOM không ảnh hưởng trực tiếp đến cấu trúc của tài liệu Word. Tuy nhiên, nó thêm một phần tử trường mới vào nội dung tài liệu. Bạn có thể thao tác cấu trúc tài liệu bằng cách thêm, xóa hoặc sửa đổi các thành phần hiện có theo nhu cầu của mình.