---
title: Chèn trường TOA mà không cần Trình tạo tài liệu
linktitle: Chèn trường TOA mà không cần Trình tạo tài liệu
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước chèn trường TOA mà không cần Document Builder bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/insert-toafield-without-document-builder/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng tính năng "Chèn trường TOA" của Aspose.Words cho .NET. Thực hiện cẩn thận từng bước để có được kết quả mong muốn.

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

## Bước 3: Chèn trường TA

Chúng tôi sử dụng lớp FieldTA để chèn trường TA vào đoạn văn.

```csharp
FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";
```

## Bước 4: Thêm đoạn văn vào nội dung tài liệu

Chúng tôi thêm đoạn văn chứa trường TA vào nội dung tài liệu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Bước 5: Tạo đoạn văn cho trường TOA

Chúng ta tạo một đoạn văn mới cho trường TOA.

```csharp
para = new Paragraph(doc);
```

## Bước 6: Chèn trường TOA

Chúng tôi sử dụng lớp FieldToa để chèn trường TOA vào đoạn văn.

```csharp
FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
```

## Bước 7: Thêm đoạn văn vào nội dung tài liệu

Chúng tôi thêm đoạn văn chứa trường TOA vào nội dung tài liệu.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

## Bước 8: Cập nhật trường TOA

 Cuối cùng, chúng tôi gọi`Update()` phương pháp cập nhật trường TOA.

```csharp
fieldToa.Update();
```

### Ví dụ về mã nguồn để chèn trường TOA mà không cần Trình tạo tài liệu với Aspose.Words cho .NET

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Chúng tôi muốn chèn các trường TA và TOA như thế này:
// { TA \c 1 \l "Giá trị 0" }
// { TOA \c 1 }

FieldTA fieldTA = (FieldTA) para.AppendField(FieldType.FieldTOAEntry, false);
fieldTA.EntryCategory = "1";
fieldTA.LongCitation = "Value 0";

doc.FirstSection.Body.AppendChild(para);

para = new Paragraph(doc);

FieldToa fieldToa = (FieldToa) para.AppendField(FieldType.FieldTOA, false);
fieldToa.EntryCategory = "1";
doc.FirstSection.Body.AppendChild(para);

fieldToa.Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertTOAFieldWithoutDocumentBuilder.docx");
```

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào để tùy chỉnh giao diện của trường TOA được chèn vào tài liệu Word bằng Aspose.Words for .NET?

Đáp: Bạn có thể tùy chỉnh hình thức của trường TOA được chèn bằng cách sử dụng các thuộc tính của`FieldTOA` đối tượng để chỉ định các tùy chọn định dạng.

#### Câu hỏi: Tôi có thể thêm nhiều trường TOA vào một tài liệu Word bằng Aspose.Words cho .NET không?

Đáp: Có, bạn có thể thêm nhiều trường TOA vào một tài liệu Word bằng Aspose.Words for .NET. Chỉ cần lặp lại các bước chèn cho từng trường.

#### Câu hỏi: Làm cách nào để kiểm tra xem trường TOA đã được chèn thành công vào tài liệu Word bằng Aspose.Words cho .NET hay chưa?

Đáp: Để kiểm tra xem trường TOA đã được chèn thành công hay chưa, bạn có thể duyệt nội dung tài liệu và tìm kiếm các phiên bản trường TOA.

#### Câu hỏi: Việc chèn trường TOA mà không sử dụng DocumentBuilder có ảnh hưởng đến định dạng tài liệu Word bằng Aspose.Words cho .NET không?

Trả lời: Việc chèn trường TOA mà không sử dụng DocumentBuilder không ảnh hưởng trực tiếp đến định dạng của tài liệu Word. Tuy nhiên, các tùy chọn định dạng trường TOA có thể ảnh hưởng đến định dạng tổng thể của tài liệu.