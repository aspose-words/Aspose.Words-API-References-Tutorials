---
title: Sửa đổi kiểm soát nội dung
linktitle: Sửa đổi kiểm soát nội dung
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách sửa đổi thẻ tài liệu có cấu trúc trong Word bằng Aspose.Words cho .NET. Cập nhật văn bản, danh sách thả xuống và hình ảnh theo từng bước.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/modify-content-controls/
---
## Giới thiệu

Nếu bạn đã từng làm việc với tài liệu Word và cần sửa đổi các điều khiển nội dung có cấu trúc—như văn bản thuần túy, danh sách thả xuống hoặc hình ảnh—bằng Aspose.Words dành cho .NET, thì bạn đã đến đúng nơi! Thẻ tài liệu có cấu trúc (SDT) là công cụ mạnh mẽ giúp việc tự động hóa tài liệu trở nên dễ dàng và linh hoạt hơn. Trong hướng dẫn này, chúng tôi sẽ đi sâu vào cách bạn có thể sửa đổi các SDT này để phù hợp với nhu cầu của mình. Cho dù bạn đang cập nhật văn bản, thay đổi lựa chọn thả xuống hay hoán đổi hình ảnh, hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình theo từng bước.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào việc sửa đổi các điều khiển nội dung, hãy đảm bảo bạn có những điều sau:

1.  Đã cài đặt Aspose.Words cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Words. Nếu không, bạn có thể[tải nó ở đây](https://releases.aspose.com/words/net/).

2. Kiến thức cơ bản về C#: Hướng dẫn này giả định rằng bạn đã quen thuộc với các khái niệm lập trình C# cơ bản.

3. Môi trường phát triển .NET: Bạn nên cài đặt một IDE như Visual Studio để chạy các ứng dụng .NET.

4. Tài liệu mẫu: Chúng tôi sẽ sử dụng tài liệu Word mẫu với nhiều loại SDT khác nhau. Bạn có thể sử dụng cái từ ví dụ hoặc tạo cái của riêng bạn.

5.  Truy cập vào Tài liệu Aspose: Để biết thêm thông tin chi tiết, hãy xem[Tài liệu Aspose.Words](https://reference.aspose.com/words/net/).

## Nhập không gian tên

Để bắt đầu làm việc với Aspose.Words, bạn cần nhập các vùng tên có liên quan vào dự án C# của mình. Đây là cách bạn làm điều đó:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Các không gian tên này sẽ cung cấp cho bạn quyền truy cập vào các lớp và phương thức cần thiết để thao tác các thẻ tài liệu có cấu trúc trong tài liệu Word của bạn.

## Bước 1: Thiết lập đường dẫn tài liệu của bạn

 Trước khi thực hiện bất kỳ thay đổi nào, bạn cần chỉ định đường dẫn đến tài liệu của mình. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế nơi tài liệu của bạn được lưu trữ.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Structured document tags.docx");
```

## Bước 2: Lặp qua các thẻ tài liệu có cấu trúc

 Để sửa đổi SDT, trước tiên bạn cần duyệt qua tất cả SDT trong tài liệu. Việc này được thực hiện bằng cách sử dụng`GetChildNodes` phương pháp để có được tất cả các nút thuộc loại`StructuredDocumentTag`.

```csharp
foreach (StructuredDocumentTag sdt in doc.GetChildNodes(NodeType.StructuredDocumentTag, true))
{
    // Sửa đổi SDT dựa trên loại của chúng
}
```

## Bước 3: Sửa đổi SDT văn bản thuần túy

Nếu SDT là loại văn bản thuần túy, bạn có thể thay thế nội dung của nó. Đầu tiên, xóa nội dung hiện có, sau đó thêm văn bản mới.

```csharp
if (sdt.SdtType == SdtType.PlainText)
{
    sdt.RemoveAllChildren();
    Paragraph para = sdt.AppendChild(new Paragraph(doc)) as Paragraph;
    Run run = new Run(doc, "new text goes here");
    para.AppendChild(run);
}
```

 Giải thích: Ở đây,`RemoveAllChildren()`xóa nội dung hiện có của SDT. Sau đó chúng tôi tạo một cái mới`Paragraph`Và`Run` đối tượng để chèn văn bản mới.

## Bước 4: Sửa đổi SDT danh sách thả xuống

 Đối với SDT danh sách thả xuống, bạn có thể thay đổi mục đã chọn bằng cách truy cập`ListItems` bộ sưu tập. Ở đây, chúng tôi chọn mục thứ ba trong danh sách.

```csharp
if (sdt.SdtType == SdtType.DropDownList)
{
    SdtListItem secondItem = sdt.ListItems[2];
    sdt.ListItems.SelectedValue = secondItem;
}
```

Giải thích: Đoạn mã này chọn mục ở chỉ mục 2 (mục thứ ba) từ danh sách thả xuống. Điều chỉnh chỉ mục dựa trên nhu cầu của bạn.

## Bước 5: Sửa đổi SDT hình ảnh

Để cập nhật hình ảnh trong SDT hình ảnh, bạn có thể thay thế hình ảnh hiện có bằng hình ảnh mới.

```csharp
if (sdt.SdtType == SdtType.Picture)
{
    Shape shape = (Shape) sdt.GetChild(NodeType.Shape, 0, true);
    if (shape.HasImage)
    {
        shape.ImageData.SetImage(ImagesDir + "Watermark.png");
    }
}
```

 Giải thích: Mã này kiểm tra xem hình có chứa hình ảnh hay không và sau đó thay thế nó bằng một hình ảnh mới nằm ở`ImagesDir`.

## Bước 6: Lưu tài liệu đã sửa đổi của bạn

Sau khi thực hiện tất cả các thay đổi cần thiết, hãy lưu tài liệu đã sửa đổi bằng tên mới để giữ nguyên tài liệu gốc của bạn.

```csharp
doc.Save(dataDir + "WorkingWithSdt.ModifyContentControls.docx");
```

Giải thích: Thao tác này sẽ lưu tài liệu bằng tên tệp mới để bạn có thể dễ dàng phân biệt nó với tên gốc.

## Phần kết luận

Việc sửa đổi các điều khiển nội dung trong tài liệu Word bằng Aspose.Words dành cho .NET rất đơn giản khi bạn hiểu các bước liên quan. Cho dù bạn đang cập nhật văn bản, thay đổi lựa chọn thả xuống hay hoán đổi hình ảnh, Aspose.Words đều cung cấp API mạnh mẽ cho những tác vụ này. Bằng cách làm theo hướng dẫn này, bạn có thể quản lý và tùy chỉnh hiệu quả các điều khiển nội dung có cấu trúc của tài liệu, làm cho tài liệu của bạn trở nên năng động hơn và phù hợp hơn với nhu cầu của bạn.

## Câu hỏi thường gặp

1. Thẻ tài liệu có cấu trúc (SDT) là gì?

SDT là các thành phần trong tài liệu Word giúp quản lý và định dạng nội dung tài liệu, như hộp văn bản, danh sách thả xuống hoặc hình ảnh.

2. Làm cách nào tôi có thể thêm mục thả xuống mới vào SDT?

 Để thêm một mục mới, hãy sử dụng`ListItems` thuộc tính và thêm một thuộc tính mới`SdtListItem` đến bộ sưu tập.

3. Tôi có thể sử dụng Aspose.Words để xóa SDT khỏi tài liệu không?

Có, bạn có thể xóa SDT bằng cách truy cập các nút của tài liệu và xóa SDT mong muốn.

4. Làm cách nào để xử lý các SDT được lồng trong các phần tử khác?

 Sử dụng`GetChildNodes` phương thức với các tham số thích hợp để truy cập các SDT lồng nhau.

5. Tôi nên làm gì nếu SDT tôi cần sửa đổi không hiển thị trong tài liệu?

Đảm bảo SDT không bị ẩn hoặc được bảo vệ. Kiểm tra cài đặt tài liệu và đảm bảo mã của bạn nhắm mục tiêu chính xác loại SDT.


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

Thế thôi! Bạn đã sửa đổi thành công các loại điều khiển nội dung khác nhau trong tài liệu Word của mình bằng Aspose.Words for .NET.