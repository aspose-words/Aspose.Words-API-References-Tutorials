---
title: Áp dụng viền và tô bóng cho đoạn văn trong tài liệu Word
linktitle: Áp dụng viền và tô bóng cho đoạn văn trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách áp dụng đường viền và tô bóng cho một đoạn văn trong tài liệu word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách áp dụng đường viền và tô bóng cho một đoạn văn trong tài liệu word bằng cách sử dụng chức năng của Aspose.Words cho .NET. Hãy làm theo các bước bên dưới để hiểu mã nguồn và áp dụng các thay đổi về định dạng.

## Bước 1: Tạo và cấu hình tài liệu

Để bắt đầu, hãy tạo một tài liệu mới và đối tượng DocumentBuilder liên quan. Đây là cách thực hiện:

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Cấu hình đường viền

Bây giờ hãy định cấu hình đường viền đoạn văn bằng cách chỉ định kiểu đường viền cho mỗi bên. Đây là cách thực hiện:

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## Bước 3: Thiết lập điền

Bây giờ chúng ta sẽ định cấu hình màu tô cho đoạn văn bằng cách chỉ định kết cấu và màu tô. Đây là cách thực hiện:

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## Bước 4: Thêm nội dung

Chúng tôi sẽ thêm một số nội dung được định dạng vào đoạn văn. Đây là cách thực hiện:

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## Bước 3: Lưu tài liệu

 Sau khi chèn trường biểu mẫu nhập văn bản, hãy lưu tài liệu vào vị trí mong muốn bằng cách sử dụng`Save` phương pháp. Đảm bảo cung cấp đường dẫn tệp thích hợp:

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### Mã nguồn mẫu cho Áp dụng đường viền và tô bóng cho đoạn văn bằng Aspose.Words cho .NET

Đây là mã nguồn hoàn chỉnh cho tính năng Áp dụng Đường viền và tô bóng cho Đoạn văn với Aspose.Words cho .NET:

```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## Phần kết luận

 Trong hướng dẫn này, chúng ta đã học cách áp dụng đường viền và tô bóng cho một đoạn văn trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách định cấu hình đoạn văn`Borders` Và`Shading` Properties, chúng tôi có thể đặt kiểu đường viền, màu đường và màu tô cho đoạn văn. Aspose.Words for .NET cung cấp khả năng định dạng mạnh mẽ để tùy chỉnh giao diện của các đoạn văn và nâng cao khả năng trình bày trực quan cho tài liệu của bạn.

### Câu hỏi thường gặp

#### Hỏi: Làm cách nào để áp dụng đường viền và bóng cho một đoạn trong tài liệu Word bằng Aspose.Words cho .NET?

Trả lời: Để áp dụng đường viền và bóng cho một đoạn trong tài liệu Word bằng Aspose.Words cho .NET, hãy làm theo các bước sau:
1.  Tạo một tài liệu mới và một`DocumentBuilder` sự vật.
2.  Định cấu hình đường viền đoạn văn bằng cách truy cập`Borders` tài sản của`ParagraphFormat` và thiết lập kiểu đường viền cho mỗi bên.
3. Định cấu hình điền đoạn văn bằng cách truy cập`Shading` tài sản của`ParagraphFormat` và chỉ định kết cấu và màu tô.
4.  Thêm nội dung vào đoạn văn bằng cách sử dụng`Write` phương pháp của`DocumentBuilder`.
5.  Lưu tài liệu bằng cách sử dụng`Save` phương pháp.

#### Hỏi: Làm cách nào để đặt kiểu đường viền cho mỗi bên của đoạn văn?

 Đáp: Để đặt kiểu đường viền cho mỗi cạnh của đoạn văn, bạn có thể truy cập vào`Borders` tài sản của`ParagraphFormat` và thiết lập`LineStyle` tài sản cho mỗi người`BorderType` (ví dụ.,`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom` ). Bạn có thể chỉ định các kiểu đường khác nhau như`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`, vân vân.

#### Hỏi: Làm cách nào để chỉ định họa tiết và màu tô cho phần tô bóng đoạn văn?

 Đáp: Để chỉ định kết cấu và màu tô cho phần tô bóng đoạn văn, bạn có thể truy cập vào`Shading` tài sản của`ParagraphFormat` và thiết lập`Texture` thuộc tính thành chỉ mục kết cấu mong muốn (ví dụ:`TextureIndex.TextureDiagonalCross` ). Bạn cũng có thể thiết lập`BackgroundPatternColor` Và`ForegroundPatternColor` thuộc tính với màu sắc mong muốn bằng cách sử dụng`System.Drawing.Color` lớp học.