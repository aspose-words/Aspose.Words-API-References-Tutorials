---
title: Trường biểu mẫu Nhận theo tên
linktitle: Trường biểu mẫu Nhận theo tên
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách truy xuất và sửa đổi các trường biểu mẫu theo tên trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/working-with-formfields/form-fields-get-by-name/
---

Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng Aspose.Words cho .NET để truy xuất các trường biểu mẫu theo tên từ tài liệu Word. Chúng tôi sẽ giải thích mã nguồn C# được cung cấp và chỉ cho bạn cách triển khai nó trong các dự án của riêng bạn.

 Để bắt đầu, hãy đảm bảo bạn đã cài đặt và thiết lập Aspose.Words for .NET trong môi trường phát triển của mình. Nếu bạn chưa làm như vậy, hãy tải xuống và cài đặt thư viện từ[Aspose.Releases]https://releases.aspose.com/words/net/.

## Bước 1: Khởi tạo đối tượng tài liệu

 Đầu tiên, khởi tạo`Document` đối tượng bằng cách cung cấp đường dẫn đến tài liệu nguồn chứa các trường biểu mẫu:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Bước 2: Truy xuất các trường biểu mẫu

 Tiếp theo, truy cập vào`FormFields` tài sản của`Range` đối tượng trong tài liệu để truy xuất tất cả các trường biểu mẫu:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Bạn có thể truy xuất các trường biểu mẫu theo chỉ mục hoặc theo tên. Trong ví dụ này, chúng tôi truy xuất trường biểu mẫu bằng cả hai phương pháp:

```csharp
FormField formField1 = documentFormFields[3]; // Truy xuất theo chỉ mục
FormField formField2 = documentFormFields["Text2"]; // Truy xuất theo tên
```

## Bước 3: Sửa đổi thuộc tính trường biểu mẫu

Khi bạn đã truy xuất các trường của biểu mẫu, bạn có thể sửa đổi các thuộc tính của chúng nếu cần. Trong ví dụ này, chúng tôi thay đổi kích thước phông chữ của`formField1` đến 20 và màu phông chữ của`formField2` sang màu đỏ:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Bước 4: Lưu tài liệu

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Đó là nó! Bạn đã truy xuất thành công các trường biểu mẫu theo tên và sửa đổi thuộc tính của chúng trong tài liệu Word bằng Aspose.Words for .NET.

### Mã nguồn ví dụ cho Trường biểu mẫu Nhận theo tên bằng Aspose.Words cho .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Vui lòng sử dụng mã này trong các dự án của riêng bạn và sửa đổi nó theo yêu cầu cụ thể của bạn.

### Câu hỏi thường gặp

#### Câu hỏi: Làm cách nào tôi có thể lấy trường biểu mẫu theo tên trong Aspose.Words?

 Trả lời: Để lấy trường biểu mẫu theo tên trong Aspose.Words, bạn có thể sử dụng`Document.Range.FormFields[name]` phương pháp. Phương thức này trả về trường biểu mẫu tương ứng với tên đã chỉ định.

#### Hỏi: Điều gì sẽ xảy ra nếu trường biểu mẫu có tên được chỉ định không tồn tại trong tài liệu?

 Trả lời: Nếu trường biểu mẫu có tên được chỉ định không tồn tại trong tài liệu, thì`Document.Range.FormFields[name]` phương thức sẽ trở lại`null`. Bạn có thể kiểm tra kết quả này để xử lý các trường hợp không tìm thấy trường biểu mẫu.

#### Câu hỏi: Làm cách nào tôi có thể sửa đổi các thuộc tính của trường biểu mẫu được tìm thấy?

Đáp: Sau khi nhận được trường biểu mẫu theo tên, bạn có thể truy cập các thuộc tính riêng lẻ của trường đó để chỉnh sửa chúng. Ví dụ: bạn có thể thay đổi giá trị của trường, bật hoặc tắt khả năng hiển thị của trường hoặc sửa đổi các thuộc tính khác nếu cần.

#### Câu hỏi: Tôi có thể lấy nhiều trường biểu mẫu có cùng tên trong tài liệu không?

 Đáp: Có, có thể có nhiều trường biểu mẫu có cùng tên trong một tài liệu. Trong trường hợp này,`Document.Range.FormFields[name]` phương thức sẽ trả về trường biểu mẫu đầu tiên được tìm thấy với tên đã chỉ định. Nếu bạn có nhiều trường biểu mẫu có cùng tên, bạn sẽ cần tính đến điều này khi thao tác với các trường.

#### Câu hỏi: Làm cách nào tôi có thể lặp lại tất cả các trường biểu mẫu trong tài liệu?

 Trả lời: Để lặp lại tất cả các trường biểu mẫu trong tài liệu, bạn có thể sử dụng`foreach` vòng lặp trên`Document.Range.FormFields` bộ sưu tập. Điều này sẽ cho phép bạn truy cập từng trường biểu mẫu riêng lẻ và thực hiện các thao tác trên từng trường đó.