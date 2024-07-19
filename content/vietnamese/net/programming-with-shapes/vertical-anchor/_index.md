---
title: Neo dọc
linktitle: Neo dọc
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách định vị hình theo chiều dọc trong tài liệu bằng tính năng neo dọc trong Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/vertical-anchor/
---

Hướng dẫn này giải thích cách sử dụng tính năng neo dọc trong Aspose.Words cho .NET để định vị hình dạng theo chiều dọc trong tài liệu. Bằng cách đặt thuộc tính neo dọc của hình, bạn có thể kiểm soát căn chỉnh dọc của hình đó so với văn bản hoặc trang.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"`với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu mới và DocumentBuilder
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` đối tượng làm việc với tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn và định cấu hình hình dạng
 Chèn một hình vào tài liệu bằng cách sử dụng`InsertShape` phương pháp của`DocumentBuilder` sự vật. Đặt kích thước mong muốn cho hình dạng.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Bước 4: Đặt neo dọc
Đặt thuộc tính neo dọc của hình để kiểm soát căn chỉnh dọc của nó. Trong ví dụ này, chúng tôi đặt nó thành "Dưới cùng" để neo hình dạng ở cuối văn bản hoặc trang.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Bước 5: Thêm nội dung vào hình dạng
 Sử dụng`MoveTo` phương pháp của`DocumentBuilder` đối tượng để di chuyển con trỏ đến đoạn đầu tiên của hình. Sau đó, sử dụng`Write` phương pháp thêm nội dung vào hình dạng.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Bước 6: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save`phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Mã nguồn mẫu cho Neo dọc sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Đó là nó! Bạn đã sử dụng thành công tính năng neo dọc trong Aspose.Words for .NET để định vị hình dạng theo chiều dọc trong tài liệu.