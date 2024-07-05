---
title: Nhận điểm giới hạn hình dạng thực tế
linktitle: Nhận điểm giới hạn hình dạng thực tế
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách truy xuất giới hạn thực tế của hình dạng theo điểm (đơn vị đo lường) trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/get-actual-shape-bounds-points/
---

Hướng dẫn này giải thích cách truy xuất giới hạn thực tế của hình dạng theo điểm (đơn vị đo lường) trong tài liệu Word bằng Aspose.Words cho .NET. Các giới hạn thể hiện kích thước và vị trí của hình dạng trong tài liệu.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Tạo một tài liệu mới và DocumentBuilder
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder`đối tượng làm việc với tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Chèn hình ảnh
 Sử dụng`InsertImage` phương pháp của`DocumentBuilder` đối tượng để chèn hình ảnh vào tài liệu. Cung cấp đường dẫn đến tệp hình ảnh làm tham số.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## Bước 3: Truy xuất điểm giới hạn hình dạng thực tế
 Truy cập hình dạng`ShapeRenderer` sử dụng`GetShapeRenderer` phương pháp. Sau đó, truy xuất các giới hạn thực tế của hình dạng theo các điểm bằng cách sử dụng`BoundsInPoints` tài sản.

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Mã nguồn ví dụ về Nhận điểm giới hạn hình dạng thực tế bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

Đó là nó! Bạn đã truy xuất thành công giới hạn thực tế của hình dạng theo điểm trong tài liệu Word của mình bằng Aspose.Words for .NET.