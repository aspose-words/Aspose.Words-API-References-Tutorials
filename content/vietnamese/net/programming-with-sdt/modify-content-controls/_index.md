---
title: Sửa đổi kiểm soát nội dung
linktitle: Sửa đổi kiểm soát nội dung
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sửa đổi văn bản, danh sách thả xuống và hình ảnh trong điều khiển nội dung trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/modify-content-controls/
---

Hướng dẫn này giải thích cách sửa đổi các loại điều khiển nội dung khác nhau trong tài liệu Word bằng Aspose.Words cho .NET. Bạn có thể cập nhật văn bản, giá trị đã chọn của danh sách thả xuống hoặc thay thế hình ảnh trong điều khiển nội dung.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu và lặp lại các điều khiển nội dung
 Tải tài liệu Word bằng cách sử dụng`Document`hàm tạo, chuyển đường dẫn đến tài liệu dưới dạng tham số. Lặp lại tất cả các thẻ tài liệu có cấu trúc trong tài liệu bằng cách sử dụng`foreach` vòng.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Thực hiện các hành động dựa trên loại kiểm soát nội dung
}
```

## Bước 3: Sửa đổi Kiểm soát nội dung văn bản thuần túy
 Đối với các điều khiển nội dung thuộc loại`SdtType.PlainText`, xóa tất cả các phần tử con hiện có, tạo một đoạn văn mới và nối thêm một đoạn văn bản mong muốn.

```csharp
case SdtType.PlainText:
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
    break;
}
```

## Bước 4: Sửa đổi Kiểm soát nội dung danh sách thả xuống
 Đối với các điều khiển nội dung thuộc loại`SdtType.DropDownList` , hãy cập nhật giá trị đã chọn bằng cách đặt nó thành một giá trị cụ thể`SdtListItem`.

```csharp
case SdtType.DropDownList:
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
    break;
}
```

## Bước 5: Sửa đổi Kiểm soát Nội dung Hình ảnh
 Đối với các điều khiển nội dung thuộc loại`SdtType.Picture`, truy xuất hình dạng trong điều khiển nội dung và thay thế hình ảnh của nó bằng hình ảnh mới.

```csharp
case SdtType.Picture:
{
    Shape shape = (Shape)sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
    break;
}
```

## Bước 6: Lưu tài liệu đã sửa đổi
 Lưu tài liệu đã sửa đổi vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.ModifyContentControls.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

### Mã nguồn mẫu cho Sửa đổi Điều khiển nội dung bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
	{
		switch (sdt.SdtType)
		{
			case SdtType.PlainText:
			{
				sdt.RemoveAllChildren();
				Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
				Run run = new Run(doc, "new text goes here");
				para.AppendChild(run);
				break;
			}
			case SdtType.DropDownList:
			{
				SdtListItem secondItem = sdt.ListItems[2];
				sdt.ListItems.SelectedValue = secondItem;
				break;
			}
			case SdtType.Picture:
			{
				Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
				if (shape.HasImage)
				{
					shape.ImageData.SetImage(ImagesDir + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");

```

Đó là nó! Bạn đã sửa đổi thành công các loại điều khiển nội dung khác nhau trong tài liệu Word của mình bằng Aspose.Words for .NET.