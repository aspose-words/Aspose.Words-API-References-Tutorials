---
title: Các vùng có thể chỉnh sửa không hạn chế trong tài liệu Word
linktitle: Các vùng có thể chỉnh sửa không hạn chế trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo các vùng có thể chỉnh sửa không hạn chế trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/document-protection/unrestricted-editable-regions/
---
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn các bước để sử dụng tính năng vùng có thể chỉnh sửa không hạn chế của Aspose.Words cho .NET. Tính năng này cho phép bạn xác định các khu vực trong tài liệu Word nơi nội dung có thể được chỉnh sửa mà không bị hạn chế, ngay cả khi phần còn lại của tài liệu ở chế độ chỉ đọc. Làm theo các bước dưới đây:

## Bước 1: Tải tài liệu và cài đặt bảo vệ

Bắt đầu bằng cách tải tài liệu hiện có:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Bảo vệ tài liệu bằng cách đặt loại và mật khẩu bảo vệ chỉ đọc

## Bước 2: Tạo vùng có thể chỉnh sửa

Bắt đầu bằng cách tạo một vùng có thể chỉnh sửa bằng cách sử dụng các đối tượng EditableRangeStart và EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Một đối tượng EditableRange được tạo cho EditableRangeStart mà chúng ta vừa tạo.
EditableRange editableRange = edRangeStart.EditableRange;

// Đặt nội dung nào đó vào trong phạm vi có thể chỉnh sửa.
builder.Writeln("Paragraph inside first editable range");

// Một phạm vi có thể chỉnh sửa được coi là hợp lệ nếu nó có phần đầu và phần cuối.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Bước 3: Thêm nội dung bên ngoài vùng có thể chỉnh sửa

Bạn có thể thêm nội dung bên ngoài vùng có thể chỉnh sửa, nội dung này sẽ vẫn ở chế độ chỉ đọc:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Bước 4: Lưu tài liệu

Cuối cùng, lưu tài liệu đã sửa đổi:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Đảm bảo chỉ định đường dẫn và tên tệp chính xác để lưu tài liệu với các vùng có thể chỉnh sửa.

### Mã nguồn ví dụ cho Vùng có thể chỉnh sửa không hạn chế bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho các vùng có thể chỉnh sửa không hạn chế bằng Aspose.Words cho .NET:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Tải lên một tài liệu và đặt nó ở dạng chỉ đọc.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Bắt đầu một phạm vi có thể chỉnh sửa.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Một đối tượng EditableRange được tạo cho EditableRangeStart mà chúng ta vừa tạo.
EditableRange editableRange = edRangeStart.EditableRange;

// Đặt nội dung nào đó vào trong phạm vi có thể chỉnh sửa.
builder.Writeln("Paragraph inside first editable range");

// Một phạm vi có thể chỉnh sửa được coi là hợp lệ nếu nó có phần đầu và phần cuối.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Bằng cách làm theo các bước này, bạn có thể dễ dàng tạo các vùng có thể chỉnh sửa không hạn chế trong tài liệu Word của mình bằng Aspose.Words for .NET.

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách tạo các vùng có thể chỉnh sửa không hạn chế trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo các bước được cung cấp, bạn có thể xác định các khu vực cụ thể trong tài liệu nơi người dùng có thể tự do chỉnh sửa nội dung trong khi vẫn giữ phần còn lại của tài liệu ở chế độ chỉ đọc. Aspose.Words for .NET cung cấp các tính năng mạnh mẽ để bảo vệ và tùy chỉnh tài liệu, cung cấp cho bạn quyền kiểm soát khả năng chỉnh sửa tài liệu Word của mình.

### Câu hỏi thường gặp về các vùng có thể chỉnh sửa không hạn chế trong tài liệu word

#### Câu hỏi: Vùng có thể chỉnh sửa không hạn chế trong Aspose.Words dành cho .NET là gì?

Trả lời: Các vùng có thể chỉnh sửa không hạn chế trong Aspose.Words dành cho .NET là các vùng trong tài liệu Word nơi nội dung có thể được chỉnh sửa mà không có bất kỳ hạn chế nào, ngay cả khi phần còn lại của tài liệu được đặt ở chế độ chỉ đọc. Các vùng này cung cấp cách xác định các phần cụ thể của tài liệu mà người dùng có thể sửa đổi trong khi vẫn duy trì khả năng bảo vệ tài liệu tổng thể.

#### Câu hỏi: Làm cách nào tôi có thể tạo các vùng có thể chỉnh sửa không hạn chế bằng Aspose.Words cho .NET?

Trả lời: Để tạo các vùng có thể chỉnh sửa không hạn chế trong tài liệu Word bằng Aspose.Words cho .NET, bạn có thể làm theo các bước sau:
1.  Tải tài liệu hiện có bằng cách sử dụng`Document` lớp học.
2.  Đặt bảo vệ tài liệu thành chỉ đọc bằng cách sử dụng`Protect` phương pháp của`Document` sự vật.
3.  Sử dụng`DocumentBuilder` lớp để tạo một phạm vi có thể chỉnh sửa bằng cách thêm một`EditableRangeStart` đối tượng và một`EditableRangeEnd` sự vật.
4.  Thêm nội dung trong phạm vi có thể chỉnh sửa bằng cách sử dụng`DocumentBuilder`.
5.  Lưu tài liệu đã sửa đổi bằng cách sử dụng`Save` phương pháp của`Document` sự vật.

#### Hỏi: Tôi có thể có nhiều vùng có thể chỉnh sửa không hạn chế trong tài liệu Word không?

Trả lời: Có, bạn có thể có nhiều vùng có thể chỉnh sửa không hạn chế trong tài liệu Word. Để đạt được điều này, bạn có thể tạo nhiều bộ`EditableRangeStart` Và`EditableRangeEnd` các đối tượng sử dụng`DocumentBuilder` lớp học. Mỗi bộ đối tượng sẽ xác định một vùng có thể chỉnh sửa riêng biệt nơi người dùng có thể sửa đổi nội dung mà không có bất kỳ hạn chế nào.

#### Câu hỏi: Tôi có thể lồng các vùng có thể chỉnh sửa vào nhau được không?

 Đáp: Không, bạn không thể lồng các vùng có thể chỉnh sửa vào nhau bằng Aspose.Words for .NET. Mỗi vùng có thể chỉnh sửa được xác định bởi một`EditableRangeStart` Và`EditableRangeEnd` cặp phải độc lập và không chồng chéo hoặc được lồng trong một vùng có thể chỉnh sửa khác. Các vùng có thể chỉnh sửa lồng nhau không được hỗ trợ.

#### Câu hỏi: Tôi có thể xóa chế độ bảo vệ chỉ đọc khỏi tài liệu trong vùng có thể chỉnh sửa không?

Trả lời: Không, bạn không thể xóa chế độ bảo vệ chỉ đọc khỏi tài liệu trong vùng có thể chỉnh sửa. Tính năng bảo vệ chỉ đọc được áp dụng cho toàn bộ tài liệu và không thể xóa nó một cách có chọn lọc trong các vùng có thể chỉnh sửa cụ thể. Mục đích của các vùng có thể chỉnh sửa là cho phép sửa đổi nội dung trong khi vẫn giữ toàn bộ tài liệu ở chế độ chỉ đọc.