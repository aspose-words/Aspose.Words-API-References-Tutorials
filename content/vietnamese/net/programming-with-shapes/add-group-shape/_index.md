---
title: Thêm hình dạng nhóm
linktitle: Thêm hình dạng nhóm
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm hình dạng nhóm có nhiều hình dạng vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/add-group-shape/
---

Hướng dẫn này giải thích cách thêm hình dạng nhóm chứa nhiều hình dạng vào tài liệu Word bằng Aspose.Words cho .NET. Nhóm hình dạng cho phép bạn kết hợp và thao tác nhiều hình dạng dưới dạng một thực thể duy nhất.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"`với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo một tài liệu mới và GroupShape
 Tạo một phiên bản mới của`Document` lớp học và`GroupShape` đối tượng làm việc với tài liệu.

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## Bước 3: Tạo và thêm hình vào GroupShape
 Tạo các hình dạng riêng lẻ như`accentBorderShape`Và`actionButtonShape` sử dụng`Shape` lớp học. Tùy chỉnh thuộc tính của họ như mong muốn. Nối các hình dạng này vào`groupShape` sự vật.

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## Bước 4: Đặt kích thước cho GroupShape
Đặt chiều rộng, chiều cao và kích thước tọa độ cho`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## Bước 5: Chèn GroupShape vào Tài liệu
 Tạo một`DocumentBuilder` đối tượng và chèn`groupShape` vào tài liệu bằng cách sử dụng`InsertNode` phương pháp.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## Bước 6: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithShapes.AddGroupShape.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Mã nguồn mẫu cho Thêm hình dạng nhóm bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

Đó là nó! Bạn đã thêm thành công một nhóm hình chứa nhiều hình vào tài liệu Word của mình bằng Aspose.W