---
title: Bảo vệ chỉ đọc trong tài liệu Word
linktitle: Bảo vệ chỉ đọc trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách bảo vệ tài liệu Word chỉ đọc của bạn bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/document-protection/read-only-protection/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng bảo vệ chỉ đọc của Aspose.Words cho .NET. Tính năng này cho phép bạn tạo tài liệu Word ở chế độ chỉ đọc để ngăn chặn việc sửa đổi trái phép. Làm theo các bước dưới đây:

## Bước 1: Tạo tài liệu và áp dụng biện pháp bảo vệ

Bắt đầu bằng cách tạo một thể hiện của lớp Document và đối tượng DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Viết nội dung vào tài liệu
Sử dụng đối tượng DocumentBuilder để ghi nội dung vào tài liệu:

```csharp
builder.Write("Open document as read-only");
```

## Bước 3: Đặt mật khẩu và đặt tài liệu ở chế độ chỉ đọc

Đặt mật khẩu cho tài liệu bằng thuộc tính SetPassword() của đối tượng WriteProtection:

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

Đảm bảo thay thế "MyPassword" bằng mật khẩu thực tế bạn muốn sử dụng.

## Bước 4: Áp dụng tài liệu chỉ đọc

Đặt tài liệu ở chế độ chỉ đọc bằng cách đặt thuộc tính ReadOnly Suggested thành true:

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## Bước 5: Áp dụng bảo vệ chỉ đọc và lưu tài liệu

Cuối cùng, áp dụng chế độ bảo vệ chỉ đọc bằng phương thức Protect() của đối tượng Document:

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp để lưu tài liệu được bảo vệ.

### Mã nguồn mẫu cho Bảo vệ chỉ đọc bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh để bảo vệ chỉ đọc bằng Aspose.Words cho .NET:

```csharp

// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

// Nhập mật khẩu dài tối đa 15 ký tự.
doc.WriteProtection.SetPassword("MyPassword");

// Làm cho tài liệu ở dạng chỉ đọc.
doc.WriteProtection.ReadOnlyRecommended = true;

// Áp dụng bảo vệ ghi dưới dạng chỉ đọc.
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

Bằng cách làm theo các bước sau, bạn có thể dễ dàng bảo vệ tài liệu của mình

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá tính năng bảo vệ chỉ đọc của Aspose.Words dành cho .NET, tính năng này cho phép bạn đặt tài liệu Word ở chế độ chỉ đọc để ngăn chặn các sửa đổi trái phép. Bằng cách làm theo các bước được cung cấp, bạn có thể dễ dàng áp dụng chế độ bảo vệ chỉ đọc cho tài liệu của mình và nâng cao tính bảo mật của chúng. Bảo vệ chỉ đọc giúp đảm bảo tính toàn vẹn và chính xác của nội dung tài liệu của bạn bằng cách hạn chế khả năng chỉnh sửa. Aspose.Words for .NET cung cấp API mạnh mẽ và linh hoạt để xử lý việc bảo vệ tài liệu và hỗ trợ nhiều tính năng khác để tùy chỉnh và bảo mật tài liệu Word của bạn.

### Câu hỏi thường gặp về bảo vệ chỉ đọc trong tài liệu word

#### Câu hỏi: Bảo vệ chỉ đọc trong Aspose.Words dành cho .NET là gì?

Trả lời: Bảo vệ chỉ đọc trong Aspose.Words dành cho .NET là một tính năng cho phép bạn tạo tài liệu Word ở chế độ chỉ đọc, ngăn chặn các sửa đổi trái phép. Khi tài liệu được đặt thành chỉ đọc, người dùng có thể mở và xem tài liệu nhưng họ không thể thực hiện bất kỳ thay đổi nào đối với nội dung của tài liệu.

#### Câu hỏi: Làm cách nào tôi có thể áp dụng tính năng bảo vệ chỉ đọc cho tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Để áp dụng tính năng bảo vệ chỉ đọc cho tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tạo một thể hiện của`Document` lớp học và một`DocumentBuilder` sự vật.
2.  Sử dụng`DocumentBuilder` để ghi nội dung vào tài liệu.
3.  Đặt mật khẩu cho tài liệu bằng cách sử dụng`SetPassword` phương pháp của`WriteProtection` sự vật.
4.  Đặt`ReadOnlyRecommended` tài sản của`WriteProtection` chủ đề`true` để khuyên bạn nên mở tài liệu ở dạng chỉ đọc.
5.  Áp dụng chế độ bảo vệ chỉ đọc bằng cách sử dụng`Protect` phương pháp của`Document` đối tượng, xác định`ProtectionType` BẰNG`ReadOnly`.
6.  Lưu tài liệu được bảo vệ bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### Câu hỏi: Tôi có thể xóa chế độ bảo vệ chỉ đọc khỏi tài liệu Word bằng Aspose.Words cho .NET không?

Trả lời: Có, bạn có thể xóa chế độ bảo vệ chỉ đọc khỏi tài liệu Word bằng Aspose.Words for .NET. Để làm điều này, bạn có thể sử dụng`Unprotect` phương pháp của`Document` lớp, loại bỏ mọi biện pháp bảo vệ hiện có khỏi tài liệu.

#### Hỏi: Tôi có thể đặt mật khẩu khác để bảo vệ chỉ đọc trong tài liệu Word không?

 Trả lời: Không, tính năng bảo vệ chỉ đọc trong Aspose.Words dành cho .NET không cho phép bạn đặt mật khẩu riêng dành riêng cho tính năng bảo vệ chỉ đọc. Mật khẩu được đặt bằng cách sử dụng`SetPassword` phương pháp của`WriteProtection` đối tượng áp dụng cho việc bảo vệ tài liệu tổng thể, bao gồm cả bảo vệ chỉ đọc và bảo vệ đọc-ghi.

#### Hỏi: Người dùng có thể bỏ qua chế độ bảo vệ chỉ đọc trong tài liệu Word không?

Trả lời: Tính năng bảo vệ chỉ đọc trong tài liệu Word nhằm mục đích ngăn cản và ngăn chặn những sửa đổi vô tình hoặc trái phép. Mặc dù nó cung cấp một mức độ bảo vệ nhưng người dùng có đủ kiến thức kỹ thuật hoặc quyền chỉnh sửa có thể bỏ qua nó. Tuy nhiên, chế độ bảo vệ chỉ đọc đóng vai trò ngăn chặn và giúp duy trì tính toàn vẹn của tài liệu.