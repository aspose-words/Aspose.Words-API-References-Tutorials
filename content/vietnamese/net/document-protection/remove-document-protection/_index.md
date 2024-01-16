---
title: Loại bỏ bảo vệ tài liệu trong tài liệu Word
linktitle: Loại bỏ bảo vệ tài liệu trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách loại bỏ tính năng bảo vệ trong tài liệu Word bằng Aspose.Words dành cho .NET.
type: docs
weight: 10
url: /vi/net/document-protection/remove-document-protection/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước sử dụng tính năng tài liệu không được bảo vệ của Aspose.Words cho .NET. Tính năng này cho phép bạn loại bỏ bảo vệ trong tài liệu Word để có thể truy cập được để chỉnh sửa thêm. Làm theo các bước dưới đây:

## Bước 1: Tạo tài liệu và thêm nội dung

Bắt đầu bằng cách tạo một thể hiện của lớp Document và đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Thêm nội dung vào tài liệu

Sử dụng đối tượng DocumentBuilder để thêm nội dung vào tài liệu:

```csharp
builder.Writeln("Text added to a document.");
```

## Bước 3: Bỏ bảo vệ tài liệu

Để bỏ bảo vệ tài liệu, bạn có thể sử dụng phương thức Unprotect() của đối tượng Document. Bạn có thể chọn loại bỏ bảo vệ mà không cần mật khẩu hoặc bằng mật khẩu chính xác. Loại bỏ bảo vệ không cần mật khẩu:

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

Đảm bảo thay thế "newPassword" bằng mật khẩu tài liệu chính xác.

## Bước 4: Lưu tài liệu mà không cần bảo vệ

Cuối cùng, lưu tài liệu không được bảo vệ bằng phương thức Save() của đối tượng Document:

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp để lưu tài liệu không được bảo vệ.

### Mã nguồn mẫu cho Xóa bảo vệ tài liệu bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để bỏ bảo vệ tài liệu bằng Aspose.Words cho .NET:

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

// Tài liệu có thể được gỡ bỏ bảo vệ mà không cần mật khẩu hoặc bằng mật khẩu chính xác.
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

Bằng cách làm theo các bước này, bạn có thể dễ dàng loại bỏ tính năng bảo vệ khỏi tài liệu Word bằng Aspose.Words cho .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách loại bỏ bảo vệ tài liệu trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng bỏ bảo vệ tài liệu và làm cho tài liệu đó có thể truy cập được để chỉnh sửa thêm. Aspose.Words for .NET cung cấp một API mạnh mẽ cho phép bạn thao tác cài đặt bảo vệ tài liệu và tùy chỉnh mức độ bảo mật cho tài liệu Word của bạn. Việc loại bỏ bảo vệ tài liệu giúp bạn linh hoạt sửa đổi nội dung và định dạng tài liệu khi cần.

### Câu hỏi thường gặp về loại bỏ bảo vệ tài liệu trong tài liệu word

#### Câu hỏi: Bảo vệ tài liệu trong Aspose.Words dành cho .NET là gì?

Trả lời: Bảo vệ tài liệu trong Aspose.Words for .NET đề cập đến tính năng cho phép bạn áp dụng các biện pháp bảo mật cho tài liệu Word để hạn chế chỉnh sửa, định dạng và sửa đổi nội dung. Nó giúp đảm bảo tính toàn vẹn và bảo mật của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể xóa tính năng bảo vệ tài liệu bằng Aspose.Words cho .NET?

Trả lời: Để xóa tính năng bảo vệ tài liệu bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tạo một thể hiện của`Document` lớp học và một`DocumentBuilder` sự vật.
2.  Sử dụng`DocumentBuilder` để thêm nội dung vào tài liệu.
3.  Gọi`Unprotect` phương pháp của`Document` phản đối việc loại bỏ mọi biện pháp bảo vệ hiện có khỏi tài liệu. Điều này có thể được thực hiện mà không cần mật khẩu hoặc bằng cách cung cấp mật khẩu chính xác.
4.  Lưu tài liệu không được bảo vệ bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### Hỏi: Tôi có thể loại bỏ tính năng bảo vệ khỏi tài liệu Word mà không cần mật khẩu không?

 Trả lời: Có, bạn có thể xóa tính năng bảo vệ khỏi tài liệu Word mà không cần mật khẩu bằng Aspose.Words for .NET. Bằng cách gọi`Unprotect` phương pháp của`Document`đối tượng mà không cần cung cấp mật khẩu, bạn có thể xóa tính năng bảo vệ khỏi tài liệu nếu trước đó nó được bảo vệ mà không cần mật khẩu.

#### Hỏi: Làm cách nào tôi có thể loại bỏ tính năng bảo vệ khỏi tài liệu Word bằng mật khẩu?

 Trả lời: Để loại bỏ tính năng bảo vệ khỏi tài liệu Word được bảo vệ bằng mật khẩu, bạn cần cung cấp mật khẩu chính xác khi gọi tới`Unprotect` phương pháp của`Document` sự vật. Điều này đảm bảo rằng chỉ những người dùng có mật khẩu chính xác mới có thể gỡ bỏ bảo vệ và truy cập tài liệu để chỉnh sửa.

#### Hỏi: Tôi có thể loại bỏ các loại bảo vệ cụ thể khỏi tài liệu Word không?

 Trả lời: Có, khi sử dụng Aspose.Words cho .NET, bạn có thể loại bỏ có chọn lọc các loại bảo vệ cụ thể khỏi tài liệu Word. Bằng cách gọi`Unprotect` phương pháp của`Document` đối tượng, bạn có thể loại bỏ loại bảo vệ mong muốn, chẳng hạn như bảo vệ chỉ đọc hoặc bảo vệ biểu mẫu, trong khi vẫn giữ nguyên các loại bảo vệ khác.