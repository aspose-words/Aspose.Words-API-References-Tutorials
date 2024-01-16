---
title: Thêm các góc đã được cắt
linktitle: Thêm các góc đã được cắt
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm hình dạng có các góc được cắt vào tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-shapes/add-corners-snipped/
---

 Hướng dẫn này giải thích cách thêm hình có các góc được cắt vào tài liệu Word bằng Aspose.Words cho .NET. Hình dạng được cắt ở các góc có thể được tùy chỉnh và chèn bằng cách sử dụng`InsertShape` phương pháp.

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

## Bước 3: Chèn hình cắt góc
 Sử dụng`InsertShape` phương pháp của`DocumentBuilder` đối tượng để chèn một hình có các góc bị cắt. Chỉ định loại hình dạng (trong trường hợp này,`ShapeType.TopCornersSnipped`) và cung cấp kích thước mong muốn cho hình dạng.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Bước 4: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Mã nguồn ví dụ cho Thêm góc được cắt bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Đó là nó! Bạn đã thêm thành công hình dạng được cắt góc vào tài liệu Word của mình bằng Aspose.Words for .NET.