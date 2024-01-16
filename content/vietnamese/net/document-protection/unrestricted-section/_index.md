---
title: Phần không hạn chế trong tài liệu Word
linktitle: Phần không hạn chế trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xác định các phần không bị hạn chế trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/document-protection/unrestricted-section/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng phần không hạn chế của Aspose.Words cho .NET. Tính năng này cho phép bạn xác định các phần cụ thể trong tài liệu Word không được bảo vệ, ngay cả khi phần còn lại của tài liệu được bảo vệ. Làm theo các bước dưới đây:

## Bước 1: Tạo tài liệu và các phần

Bắt đầu bằng cách tạo một thể hiện của lớp Document và đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Thêm nội dung vào tài liệu
Sử dụng đối tượng DocumentBuilder để thêm nội dung vào tài liệu và chèn dấu ngắt phần:

```csharp
builder.Writeln("Section 1. Unprotected.");
builder. InsertBreak(BreakType. SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");
```

## Bước 3: Bảo vệ tài liệu và các phần

Tính năng bảo vệ phần chỉ hoạt động khi tính năng bảo vệ tài liệu được bật và chỉ cho phép chỉnh sửa trong các trường biểu mẫu. Bạn có thể bảo vệ tài liệu bằng phương thức Protect() của đối tượng Document:

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

Đảm bảo chỉ định đúng loại bảo vệ và đặt mật khẩu mong muốn.

## Bước 4: Vô hiệu hóa bảo vệ cho một phần cụ thể

Theo mặc định, tất cả các phần đều được bảo vệ, nhưng bạn có thể tắt tính năng bảo vệ một cách có chọn lọc cho một phần cụ thể bằng cách sử dụng thuộc tính ProtectedForForms của đối tượng Phần:

```csharp
doc.Sections[0].ProtectedForForms = false;
```

Trong ví dụ này, tính năng bảo vệ bị tắt đối với phần đầu tiên.

## Bước 5: Lưu tài liệu

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");
```

Đảm bảo chỉ định đường dẫn và tên tệp chính xác để lưu tài liệu với các phần không bị giới hạn.

### Mã nguồn ví dụ cho Phần không hạn chế sử dụng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho phần không hạn chế sử dụng Aspose.Words cho .NET:


```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Chèn hai phần với một số văn bản.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Section 1. Unprotected.");
builder.InsertBreak(BreakType.SectionBreakContinuous);
builder.Writeln("Section 2. Protected.");

// Tính năng bảo vệ phần chỉ hoạt động khi tính năng bảo vệ tài liệu được bật và chỉ cho phép chỉnh sửa trong các trường biểu mẫu.
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//Theo mặc định, tất cả các phần đều được bảo vệ, nhưng chúng ta có thể tắt tính năng bảo vệ một cách có chọn lọc.
doc.Sections[0].ProtectedForForms = false;
doc.Save(dataDir + "DocumentProtection.UnrestrictedSection.docx");

doc = new Document(dataDir + "DocumentProtection.UnrestrictedSection.docx");

```

Bằng cách làm theo các bước này, bạn sẽ có thể dễ dàng xác định các phần không bị hạn chế trong tài liệu Word của mình bằng Aspose.Words for .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá tính năng phần không hạn chế của Aspose.Words dành cho .NET, cho phép các phần cụ thể trong tài liệu Word không được bảo vệ trong khi phần còn lại của tài liệu được bảo vệ. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng xác định các phần trong tài liệu của mình nơi người dùng có thể tự do chỉnh sửa nội dung trong khi vẫn duy trì chế độ bảo vệ cho các phần khác. Aspose.Words for .NET cung cấp các khả năng mạnh mẽ để bảo vệ và tùy chỉnh tài liệu, cho phép bạn kiểm soát các quyền chỉnh sửa trong tài liệu Word của mình.

### Câu hỏi thường gặp về phần không hạn chế trong tài liệu word

#### Câu hỏi: Các phần không hạn chế trong Aspose.Words dành cho .NET là gì?

Đáp: Các phần không hạn chế trong Aspose.Words for .NET là các phần cụ thể trong tài liệu Word không được bảo vệ, ngay cả khi phần còn lại của tài liệu được bảo vệ. Các phần này cho phép người dùng sửa đổi nội dung trong đó trong khi vẫn duy trì khả năng bảo vệ cho các phần còn lại của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể tạo các phần không bị hạn chế bằng Aspose.Words cho .NET?

Trả lời: Để tạo các phần không bị hạn chế trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tạo một thể hiện của`Document` lớp học và một`DocumentBuilder` sự vật.
2.  Sử dụng`DocumentBuilder` để thêm nội dung vào tài liệu và chèn dấu ngắt phần.
3.  Bảo vệ tài liệu bằng cách sử dụng`Protect` phương pháp của`Document` đối tượng, chỉ định loại bảo vệ và mật khẩu mong muốn.
4.  Tắt tính năng bảo vệ cho một phần cụ thể bằng cách đặt`ProtectedForForms` thuộc tính tương ứng`Section` chủ đề`false`.
5. Lưu tài liệu đã sửa đổi.

#### Hỏi: Tôi có thể có nhiều phần không hạn chế trong tài liệu Word không?

 Đáp: Có, bạn có thể có nhiều phần không hạn chế trong tài liệu Word. Bằng cách vô hiệu hóa có chọn lọc tính năng bảo vệ cho các phần cụ thể bằng cách sử dụng`ProtectedForForms` tài sản của`Section`đối tượng, bạn có thể xác định nhiều phần trong đó người dùng có thể tự do sửa đổi nội dung trong khi vẫn bảo vệ các phần khác.

#### Q4. Tôi có thể xóa tính năng bảo vệ khỏi phần đã được bảo vệ ban đầu không?
 Có, bạn có thể xóa tính năng bảo vệ khỏi phần được bảo vệ ban đầu bằng cách đặt`ProtectedForForms` thuộc tính tương ứng`Section` chủ đề`false`. Điều này cho phép người dùng chỉnh sửa nội dung trong phần cụ thể đó mà không có bất kỳ hạn chế nào.

#### Hỏi: Những loại bảo vệ nào có thể được áp dụng cho tài liệu Word?

Trả lời: Aspose.Words for .NET cung cấp nhiều loại bảo vệ khác nhau có thể áp dụng cho tài liệu Word, bao gồm:
- NoProtection: Không có biện pháp bảo vệ nào được áp dụng.
- AllowOnlyRevisions: Người dùng chỉ có thể sửa đổi tài liệu.
- AllowOnlyComments: Người dùng chỉ có thể thêm nhận xét vào tài liệu.
- AllowOnlyFormFields: Người dùng chỉ có thể chỉnh sửa các trường biểu mẫu trong tài liệu.
- ReadOnly: Tài liệu ở chế độ chỉ đọc và không được phép chỉnh sửa.


