---
title: Chuyển đổi các trường trong đoạn văn
linktitle: Chuyển đổi các trường trong đoạn văn
second_title: API xử lý tài liệu Aspose.Words
description: Chuyển đổi các trường IF thành văn bản thuần túy trong một đoạn văn bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/convert-fields-in-paragraph/
---

Dưới đây là hướng dẫn trình bày cách sử dụng tính năng Chuyển đổi trường thành đoạn văn với Aspose.Words cho .NET. Mã này chuyển đổi tất cả các trường loại IF gặp phải trong đoạn cuối của tài liệu thành văn bản thuần túy. Hãy làm theo các bước dưới đây để hiểu và chạy mã này.

Đảm bảo bạn đã cài đặt Aspose.Words cho .NET và thiết lập môi trường phát triển của mình trước khi bắt đầu.

## Bước 1: Nhập tài liệu tham khảo

Để sử dụng Aspose.Words trong dự án của bạn, bạn cần thêm các tài liệu tham khảo cần thiết. Đảm bảo rằng bạn đã thêm tham chiếu đến thư viện Aspose.Words trong dự án của mình.

## Bước 2: Tải tài liệu

Trước khi có thể chuyển đổi các trường, bạn phải tải tài liệu chứa các trường cần chuyển đổi. Đảm bảo chỉ định đường dẫn chính xác đến thư mục chứa tài liệu. Đây là cách tải tài liệu lên:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Chuyển đổi trường thành văn bản

Bây giờ tài liệu đã được tải, chúng ta có thể tiến hành chuyển đổi các trường loại thành văn bản thuần túy. Trong ví dụ này, chúng tôi chỉ nhắm mục tiêu các trường có trong đoạn cuối của tài liệu. Đây là mã thực hiện chuyển đổi này:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

Mã này sử dụng kết hợp các phương thức LINQ để lọc ra các trường trong đoạn cuối của tài liệu và sau đó chuyển đổi chúng thành văn bản thuần túy bằng cách gọi hàm`Unlink()` phương pháp.

## Bước 4: Lưu tài liệu đã sửa đổi

 Khi các trường đã được chuyển đổi, bạn có thể lưu tài liệu đã sửa đổi. Sử dụng`Save()` phương pháp cho việc này. Đây là một ví dụ :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp để sao lưu.

### Ví dụ về mã nguồn cho Chuyển đổi trường trong đoạn văn bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu.
Document doc = new Document(dataDir + "Linked fields.docx");

// Chuyển đổi các trường IF thành văn bản thuần túy trong đoạn cuối của tài liệu.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Lưu tài liệu đã sửa đổi.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

### Câu hỏi thường gặp

#### Câu hỏi: Trường chuyển đổi trong Aspose.Words là gì?

Trả lời: Trường chuyển đổi trong Aspose.Words là loại trường chuyển đổi một giá trị hoặc biểu thức thành định dạng hoặc loại dữ liệu khác. Ví dụ: bạn có thể sử dụng trường chuyển đổi để chuyển đổi ngày sang định dạng cụ thể, số thành văn bản hoặc thực hiện các loại chuyển đổi khác.

#### Hỏi: Làm cách nào để chèn trường chuyển đổi vào đoạn văn bằng Aspose.Words?

Trả lời: Để chèn trường chuyển đổi vào đoạn văn bằng Aspose.Words, bạn có thể làm theo các bước sau:

1. Nhập lớp Tài liệu từ không gian tên Aspose.Words.
2. Tạo một phiên bản Tài liệu bằng cách tải tài liệu hiện có của bạn.
3. Lấy đoạn văn mà bạn muốn chèn trường chuyển đổi.
4. Sử dụng phương thức InsertField để chèn trường chuyển đổi với cú pháp đúng.

#### Câu hỏi: Aspose.Words hỗ trợ những định dạng chuyển đổi nào?

Trả lời: Aspose.Words hỗ trợ nhiều định dạng chuyển đổi trong các trường, bao gồm định dạng ngày, định dạng số, định dạng văn bản, định dạng tiền tệ, định dạng phần trăm, v.v. Bạn có thể kiểm tra tài liệu Aspose.Words để biết danh sách đầy đủ các định dạng chuyển đổi có sẵn.

#### Câu hỏi: Làm cách nào để cập nhật trường chuyển đổi trong tài liệu Word bằng Aspose.Words?

Trả lời: Để cập nhật trường chuyển đổi trong tài liệu Word bằng Aspose.Words, bạn có thể sử dụng phương thức UpdateFields. Phương thức này lặp qua tài liệu và cập nhật tất cả các trường, bao gồm các trường chuyển đổi, tính toán lại giá trị dựa trên dữ liệu hiện tại.