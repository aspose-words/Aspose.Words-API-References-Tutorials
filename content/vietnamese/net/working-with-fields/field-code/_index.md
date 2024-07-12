---
title: Mã trường
linktitle: Mã trường
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để lấy mã trường và kết quả trường trong tài liệu Word của bạn với Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/field-code/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng tính năng "Lấy mã trường" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã được cung cấp, bạn phải chỉ định thư mục tài liệu của mình. Thay thế giá trị "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu

Bước đầu tiên là tải tài liệu lên nơi bạn muốn lấy mã trường.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Hãy nhớ thay thế "Hyperlinks.docx" bằng tên tệp của riêng bạn.

## Bước 3: Duyệt các trường tài liệu

 Chúng tôi sử dụng một`foreach` vòng lặp để lặp qua tất cả các trường có trong tài liệu.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 Trên mỗi lần lặp của vòng lặp, chúng ta nhận được mã trường bằng cách sử dụng`GetFieldCode()` phương pháp. Chúng tôi cũng lưu trữ kết quả của trường trong một biến.

### Ví dụ về mã nguồn để lấy mã trường với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Lặp qua các trường tài liệu.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     //Làm điều gì đó với mã và kết quả của trường.
}
```

Trong ví dụ này, chúng tôi đã tải một tài liệu rồi duyệt qua tất cả các trường có trong tài liệu. Ở mỗi lần lặp, chúng tôi nhận được mã và kết quả của trường. Bạn có thể thêm logic của riêng mình để xử lý các trường mã và kết quả nếu cần.

Phần này kết thúc hướng dẫn của chúng tôi về cách sử dụng tính năng "Lấy mã trường" với Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể chèn một trường vào tài liệu Word bằng Aspose.Words cho .NET?

 Trả lời: Để chèn một trường vào tài liệu Word bằng Aspose.Words cho .NET, bạn có thể sử dụng`DocumentBuilder.InsertField` phương pháp xác định mã trường thích hợp. Ví dụ, bạn có thể sử dụng`builder.InsertField("MERGEFIELD CustomerName")` để chèn trường hợp nhất vào tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể cập nhật các trường trong tài liệu bằng Aspose.Words cho .NET?

 Trả lời: Để cập nhật các trường tài liệu bằng Aspose.Words cho .NET, bạn có thể sử dụng`Document.UpdateFields` phương pháp. Điều này sẽ cập nhật tất cả các trường có trong tài liệu, chẳng hạn như trường hợp nhất, trường ngày, v.v.

#### Câu hỏi: Làm cách nào tôi có thể truy xuất giá trị của một trường cụ thể trong Aspose.Words cho .NET?

 Trả lời: Để truy xuất giá trị của một trường cụ thể trong Aspose.Words cho .NET, bạn có thể sử dụng`Field.GetResult` phương pháp bằng cách chỉ định chỉ mục của trường trong`Document.Range.Fields` bộ sưu tập. Ví dụ, bạn có thể sử dụng`string value = document.Range.Fields[0].GetResult()` để lấy giá trị của trường đầu tiên trong tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể xóa trường khỏi tài liệu bằng Aspose.Words cho .NET?

 Trả lời: Để xóa một trường khỏi tài liệu bằng Aspose.Words cho .NET, bạn có thể sử dụng`Field.Remove` phương pháp xác định`Field` đối tượng bạn muốn loại bỏ. Thao tác này sẽ xóa trường này khỏi tài liệu.