---
title: Nhận tên trường trộn thư
linktitle: Nhận tên trường trộn thư
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách lấy tên trường phối thư trong tài liệu Word của bạn bằng Aspose.Words dành cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-fields/get-mail-merge-field-names/
---

Dưới đây là hướng dẫn từng bước để giải thích mã nguồn C# bên dưới, sử dụng tính năng "Nhận tên trường hợp nhất" của Aspose.Words cho .NET. Hãy chắc chắn làm theo từng bước một cách cẩn thận để có được kết quả mong muốn.

## Bước 1: Thiết lập thư mục tài liệu

Trong mã được cung cấp, bạn phải chỉ định thư mục tài liệu của mình. Thay thế giá trị "THƯ VIỆN TÀI LIỆU CỦA BẠN" bằng đường dẫn thích hợp tới thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Bước 2: Tải tài liệu

Bước đầu tiên là tải tài liệu mà bạn muốn lấy tên trường hợp nhất.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Đảm bảo thay thế "TỆP TÀI LIỆU CỦA BẠN" bằng tên tệp của riêng bạn.

## Bước 3: Lấy tên trường hợp nhất

 Chúng tôi sử dụng`GetFieldNames()` phương thức để lấy một mảng chứa tên của các trường hợp nhất có trong tài liệu.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 Các`fieldNames` biến hiện chứa tên của các trường hợp nhất.

### Ví dụ về mã nguồn để lấy tên trường hợp nhất với Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Nhận tên trường hợp nhất.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Hiển thị số lượng trường hợp nhất.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 Trong ví dụ này, chúng tôi đã tải một tài liệu, lấy tên trường hợp nhất bằng cách sử dụng`GetFieldNames()` phương thức và hiển thị số lượng trường hợp nhất có trong tài liệu.

Phần này kết thúc hướng dẫn của chúng tôi về cách sử dụng tính năng "Nhận tên trường hợp nhất" với Aspose.Words cho .NET.

### Câu hỏi thường gặp

#### Câu hỏi 1: Trộn thư trong Aspose.Words là gì?

Trộn thư trong Aspose.Words là một quá trình hợp nhất dữ liệu từ nguồn bên ngoài (ví dụ: bảng tính Excel hoặc cơ sở dữ liệu) với tài liệu Word mẫu để tạo tài liệu được cá nhân hóa. Điều này tạo điều kiện thuận lợi cho việc tạo thư, báo cáo và các tài liệu tương tự khác một cách tự động.

#### Câu hỏi 2: Làm cách nào để có được danh sách các trường phối thư có sẵn trong tài liệu Word?

Để có được danh sách các trường trộn thư có sẵn trong tài liệu Word, bạn có thể làm theo các bước sau:

1. Nhập các lớp Document và MailMergeFieldNames từ không gian tên Aspose.Words.
2. Tạo một phiên bản Tài liệu bằng cách tải tài liệu Word của bạn.
3. Sử dụng phương thức GetMailMergeFieldNames của đối tượng Tài liệu để lấy danh sách các trường trộn thư có sẵn.

Đây là một mã mẫu để minh họa quá trình:

```csharp
// Nhập các không gian tên cần thiết
using Aspose.Words;
using Aspose.Words.MailMerging;

// Tải tài liệu hiện có
Document document = new Document("FilePath");

// Lấy danh sách các trường trộn thư
MailMergeFieldNames fieldNames = document.MailMerge.GetFieldNames();

// Duyệt qua các trường phối thư có sẵn
foreach (string fieldName in fieldNames)
{
     // Làm điều gì đó với tên trường
     Console.WriteLine(fieldName);
}
```
### Câu hỏi thường gặp

#### Câu hỏi: Trộn thư trong Aspose.Words là gì?

Trả lời: Trộn thư trong Aspose.Words là một quá trình hợp nhất dữ liệu từ nguồn bên ngoài (ví dụ: bảng tính Excel hoặc cơ sở dữ liệu) với tài liệu Word mẫu để tạo tài liệu được cá nhân hóa. Điều này tạo điều kiện thuận lợi cho việc tạo thư, báo cáo và các tài liệu tương tự khác một cách tự động.

#### Hỏi: Làm cách nào để có được danh sách các trường phối thư có sẵn trong tài liệu Word?

Trả lời: Để có được danh sách các trường phối thư có sẵn trong tài liệu Word, bạn có thể làm theo các bước sau:

1. Nhập các lớp Document và MailMergeFieldNames từ không gian tên Aspose.Words.
2. Tạo một phiên bản Tài liệu bằng cách tải tài liệu Word của bạn.
3. Sử dụng phương thức GetMailMergeFieldNames của đối tượng Tài liệu để lấy danh sách các trường trộn thư có sẵn.

#### Hỏi: Tôi có thể lấy trường phối thư từ nguồn dữ liệu bên ngoài như bảng tính Excel không?

Đáp: Có, bạn có thể lấy các trường phối thư từ nguồn dữ liệu bên ngoài, chẳng hạn như bảng tính Excel. Đối với điều này, bạn có thể sử dụng các tính năng liên kết dữ liệu của Aspose.Words để thiết lập kết nối với nguồn dữ liệu và lấy tên của các trường có sẵn.

#### Câu hỏi: Có thể lọc các trường trộn thư dựa trên các tiêu chí nhất định không?

Đáp: Có, có thể lọc các trường phối thư dựa trên các tiêu chí nhất định. Bạn có thể sử dụng biểu thức thông thường hoặc điều kiện cụ thể để lọc các trường phối thư và chỉ lấy những trường đáp ứng tiêu chí cụ thể của bạn.

#### Câu hỏi: Làm cách nào tôi có thể thao tác các trường trộn thư trong Aspose.Words?

Đáp: Để thao tác các trường trộn thư trong Aspose.Words, bạn có thể sử dụng các phương thức và thuộc tính được cung cấp bởi các đối tượng Document và MailMergeField. Bạn có thể thêm, xóa hoặc cập nhật các trường phối thư cũng như truy xuất và chỉnh sửa các giá trị được liên kết với các trường.