---
title: Kiểm soát nội dung loại hộp kiểm
linktitle: Kiểm soát nội dung loại hộp kiểm
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo Kiểm soát nội dung loại hộp kiểm trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/check-box-type-content-control/
---

Hướng dẫn này giải thích cách tạo Kiểm soát nội dung loại hộp kiểm trong tài liệu Word bằng Aspose.Words cho .NET. Kiểm soát nội dung hộp kiểm cho phép người dùng chọn hoặc xóa hộp kiểm trong tài liệu.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"`với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu và DocumentBuilder
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` để xây dựng nội dung của tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Thêm kiểm soát nội dung loại hộp kiểm
 Tạo một`StructuredDocumentTag` với`SdtType.Checkbox` để thể hiện việc kiểm soát nội dung hộp kiểm. Chỉ định`MarkupLevel.Inline` để đặt nó trong văn bản.

```csharp
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
builder.InsertNode(sdtCheckBox);
```

## Bước 4: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save`phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.CheckBoxTypeContentControl.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

### Mã nguồn mẫu cho Kiểm soát nội dung loại hộp kiểm bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.Checkbox, MarkupLevel.Inline);
	builder.InsertNode(sdtCheckBox);
	doc.Save(dataDir + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.Docx);
```

Đó là nó! Bạn đã tạo thành công Kiểm soát nội dung loại hộp kiểm trong tài liệu Word của mình bằng Aspose.Words cho .NET.