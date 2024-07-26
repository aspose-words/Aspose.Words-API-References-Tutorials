---
title: Tỷ lệ khung hình đã bị khóa
linktitle: Tỷ lệ khung hình đã bị khóa
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách khóa hoặc mở khóa tỷ lệ khung hình của hình dạng trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/aspect-ratio-locked/
---

Hướng dẫn này giải thích cách khóa hoặc mở khóa tỷ lệ khung hình của hình dạng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách khóa tỷ lệ khung hình, bạn có thể duy trì tỷ lệ ban đầu của hình khi thay đổi kích thước.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu mới và DocumentBuilder
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` đối tượng làm việc với tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn hình ảnh
 Sử dụng`InsertImage` phương pháp của`DocumentBuilder` đối tượng để chèn hình ảnh vào tài liệu. Cung cấp đường dẫn đến tệp hình ảnh làm tham số.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Bước 4: Khóa hoặc mở khóa tỷ lệ khung hình
 Đặt`AspectRatioLocked` thuộc tính của hình dạng`true` hoặc`false` để khóa hoặc mở khóa tỷ lệ khung hình tương ứng.

```csharp
shape.AspectRatioLocked = false; // Mở khóa tỷ lệ khung hình
```

## Bước 5: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Mã nguồn mẫu cho Tỷ lệ khung hình bị khóa bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Đó là nó! Bạn đã khóa hoặc mở khóa thành công tỷ lệ khung hình của hình trong tài liệu Word bằng Aspose.Words for .NET.