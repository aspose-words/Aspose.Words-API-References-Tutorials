---
title: Thêm hình mờ văn bản với các tùy chọn cụ thể
linktitle: Thêm hình mờ văn bản với các tùy chọn cụ thể
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm hình mờ văn bản với các tùy chọn cụ thể bằng Aspose.Words cho .NET. Hướng dẫn từng bước một.
type: docs
weight: 10
url: /vi/net/programming-with-watermark/add-text-watermark-with-specific-options/
---

Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thêm hình mờ văn bản với các tùy chọn cụ thể bằng Aspose.Words cho .NET. Hình mờ văn bản là văn bản được đặt chồng lên một tài liệu để cho biết rằng đó là bản nháp, bí mật, v.v.

## Bước 1: Sử dụng trình tạo tài liệu

Đầu tiên, chúng tôi sẽ sử dụng trình tạo tài liệu để thêm nội dung vào tài liệu của mình.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu

Chúng tôi sẽ tải một tài liệu hiện có bằng đường dẫn tài liệu.

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

## Bước 3: Thêm hình mờ văn bản với các tùy chọn cụ thể

 Chúng ta sẽ tạo một thể hiện của`TextWatermarkOptions` class và đặt các tùy chọn mong muốn cho hình mờ văn bản.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
FontFamily = "Arial",
FontSize = 36,
Color = Color.Black,
Layout = WatermarkLayout.Horizontal,
IsSemitrasparent = false
};

doc.Watermark.SetText("Test", options);
```

## Bước 4: Lưu tài liệu

Cuối cùng, chúng ta có thể lưu tài liệu với hình mờ văn bản được thêm vào.

```csharp
	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

### Mã nguồn mẫu để thêm hình mờ văn bản với các tùy chọn cụ thể với Aspose.Words for .NET

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Document.docx");

	TextWatermarkOptions options = new TextWatermarkOptions()
	{
		FontFamily = "Arial",
		FontSize = 36,
		Color = Color.Black,
		Layout = WatermarkLayout.Horizontal,
		IsSemitrasparent = false
	};

	doc.Watermark.SetText("Test", options);

	doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
	
```

Xin chúc mừng! Bây giờ bạn đã học cách thêm hình mờ văn bản với các tùy chọn cụ thể bằng Aspose.Words cho .NET.

