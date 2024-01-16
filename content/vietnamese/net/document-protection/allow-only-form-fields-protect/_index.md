---
title: Chỉ cho phép bảo vệ các trường biểu mẫu trong tài liệu Word
linktitle: Chỉ cho phép bảo vệ các trường biểu mẫu trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sử dụng Aspose.Words cho .NET để bảo vệ trong tài liệu word và chỉ cho phép chỉnh sửa các trường biểu mẫu.
type: docs
weight: 10
url: /vi/net/document-protection/allow-only-form-fields-protect/
---
Bảo vệ tài liệu là một tính năng thiết yếu khi Xử lý văn bản với các tệp trong ứng dụng C# của bạn. Với thư viện Aspose.Words dành cho .NET, bạn có thể dễ dàng bảo vệ tài liệu của mình và chỉ cho phép chỉnh sửa các trường biểu mẫu. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn cách sử dụng mã nguồn C# để chỉ cho phép chỉnh sửa các trường biểu mẫu bằng tính năng Chỉ cho phép bảo vệ trường biểu mẫu của Aspose.Words cho .NET.

## Bước 1: Thiết lập thư mục tài liệu

Bước đầu tiên là xác định thư mục tài liệu của bạn. Bạn phải chỉ định đường dẫn nơi bạn muốn lưu tài liệu được bảo vệ. Ví dụ :

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Chèn phần và văn bản

Tiếp theo, bạn cần chèn các phần và văn bản vào tài liệu của mình. Sử dụng lớp DocumentBuilder do Aspose.Words cung cấp để xây dựng nội dung tài liệu của bạn. Đây là một ví dụ đơn giản:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

Trong ví dụ này, chúng tôi tạo một tài liệu trống mới và sau đó sử dụng DocumentBuilder để thêm một dòng văn bản.

## Bước 3: Kích hoạt bảo vệ tài liệu

 Tính năng bảo vệ tài liệu chỉ hoạt động khi tính năng bảo vệ tài liệu được bật. Bạn có thể kích hoạt tính năng bảo vệ tài liệu bằng cách sử dụng`Protect` phương thức của lớp Document. Đây là cách thực hiện:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Trong ví dụ này, chúng tôi kích hoạt bảo vệ tài liệu bằng cách chỉ định loại bảo vệ `

AllowOnlyFormFields` và đặt mật khẩu.

## Bước 4: Chỉ cho phép các trường biểu mẫu

Bây giờ tính năng bảo vệ tài liệu đã được bật, chúng tôi cần chỉ định rằng chỉ cho phép chỉnh sửa các trường biểu mẫu. Điều này đảm bảo rằng người dùng chỉ có thể chỉnh sửa các phần của tài liệu là các trường biểu mẫu. Đây là cách thực hiện:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Đảm bảo thay thế "mật khẩu" bằng mật khẩu bạn đã đặt trước đó.

## Bước 5: Lưu tài liệu được bảo vệ

 Cuối cùng, bạn có thể lưu tài liệu được bảo vệ bằng cách sử dụng`Save` phương thức của lớp Document. Chỉ định đường dẫn tệp đầy đủ và tên tệp mong muốn. Ví dụ :

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

Đảm bảo thay thế "dataDir" bằng đường dẫn đến thư mục tài liệu của bạn.

### Mã nguồn ví dụ cho tính năng Chỉ cho phép bảo vệ trường biểu mẫu bằng Aspose.Words cho .NET

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Chèn hai phần với một số văn bản.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

// Tính năng bảo vệ tài liệu chỉ hoạt động khi tính năng bảo vệ tài liệu được bật và chỉ cho phép chỉnh sửa trong các trường biểu mẫu.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

// Lưu tài liệu được bảo vệ.
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách sử dụng thư viện Aspose.Words cho .NET để bảo vệ tài liệu và chỉ cho phép chỉnh sửa các trường biểu mẫu. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng triển khai chức năng này trong ứng dụng C# của mình. Bảo vệ tài liệu là điều cần thiết để đảm bảo tính an toàn và bảo mật cho tài liệu của bạn.

### Câu hỏi thường gặp về chỉ cho phép bảo vệ các trường biểu mẫu trong tài liệu word

#### Câu hỏi: Bảo vệ tài liệu trong Aspose.Words dành cho .NET là gì?

Trả lời: Bảo vệ tài liệu trong Aspose.Words for .NET là một tính năng cho phép bạn bảo mật tài liệu của mình bằng cách hạn chế một số hành động nhất định, chẳng hạn như chỉnh sửa, định dạng hoặc sửa đổi nội dung. Nó giúp duy trì tính toàn vẹn và bảo mật của tài liệu của bạn bằng cách ngăn chặn những thay đổi trái phép.

#### Câu hỏi: Làm cách nào tôi có thể bảo vệ tài liệu và chỉ cho phép chỉnh sửa các trường biểu mẫu bằng Aspose.Words cho .NET?

Trả lời: Để bảo vệ tài liệu và chỉ cho phép chỉnh sửa các trường biểu mẫu bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1. Xác định đường dẫn thư mục cho tài liệu của bạn.
2.  Chèn các phần và văn bản vào tài liệu của bạn bằng cách sử dụng`DocumentBuilder` lớp học.
3.  Bật tính năng bảo vệ tài liệu bằng cách sử dụng`Protect` phương pháp của`Document` lớp, chỉ định loại bảo vệ là`AllowOnlyFormFields` và cung cấp mật khẩu.
4.  Lưu tài liệu được bảo vệ bằng cách sử dụng`Save` phương pháp của`Document` lớp học.

#### Câu hỏi: Tôi có thể chèn các trường biểu mẫu vào tài liệu được bảo vệ bằng Aspose.Words cho .NET không?

Trả lời: Có, bạn có thể chèn các trường biểu mẫu vào tài liệu được bảo vệ bằng Aspose.Words for .NET. Việc bảo vệ tài liệu bằng`AllowOnlyFormFields` type cho phép người dùng chỉ chỉnh sửa các trường biểu mẫu trong khi bảo vệ phần còn lại của nội dung tài liệu. Bạn có thể dùng`DocumentBuilder` class để chèn các trường biểu mẫu vào tài liệu trước khi kích hoạt tính năng bảo vệ.

#### Câu hỏi: Tôi có thể xóa tính năng bảo vệ tài liệu khỏi tài liệu được bảo vệ không?

 Trả lời: Có, bạn có thể xóa tính năng bảo vệ tài liệu khỏi tài liệu được bảo vệ bằng Aspose.Words for .NET. Để loại bỏ sự bảo vệ, bạn có thể sử dụng`Unprotect` phương pháp của`Document` lớp và cung cấp mật khẩu chính xác. Điều này sẽ loại bỏ sự bảo vệ và cho phép chỉnh sửa tài liệu không hạn chế.

#### Câu hỏi: Có thể bảo vệ một tài liệu bằng nhiều loại bảo vệ không?

 Đáp: Không, Aspose.Words for .NET chỉ cho phép áp dụng một loại bảo vệ cho một tài liệu tại một thời điểm. Tuy nhiên,`AllowOnlyFormFields` loại bảo vệ có thể hạn chế hiệu quả việc chỉnh sửa các trường biểu mẫu trong khi cho phép các loại bảo vệ khác, chẳng hạn như`AllowOnlyComments` hoặc`AllowOnlyRevisions`được kết hợp với bảo vệ trường biểu mẫu.

#### Câu hỏi: Tôi có thể đặt các mật khẩu khác nhau cho các loại bảo vệ khác nhau trong một tài liệu không?

Trả lời: Không, Aspose.Words for .NET cho phép bạn đặt một mật khẩu duy nhất để bảo vệ tài liệu, bất kể loại bảo vệ. Mật khẩu tương tự sẽ được sử dụng để bật và tắt tính năng bảo vệ tài liệu.