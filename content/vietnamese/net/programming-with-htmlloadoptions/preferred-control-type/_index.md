---
title: Loại điều khiển ưa thích trong tài liệu Word
linktitle: Loại điều khiển ưa thích trong tài liệu Word
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước để chỉ định loại điều khiển ưu tiên trong tài liệu word khi tải tài liệu HTML bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-htmlloadoptions/preferred-control-type/
---
Bài viết này cung cấp hướng dẫn từng bước về cách sử dụng tính năng loại điều khiển ưa thích với Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Ở cuối hướng dẫn này, bạn sẽ có thể hiểu cách chỉ định loại điều khiển ưa thích khi tải tài liệu HTML.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định mã HTML

 Để bắt đầu, bạn cần xác định mã HTML bạn muốn tải dưới dạng tài liệu. Trong ví dụ này, chúng tôi đã xác định một`html` biến chứa mã HTML của bộ chọn với các tùy chọn.

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## Bước 2: Đặt tùy chọn tải HTML

 Tiếp theo, chúng ta tạo một`HtmlLoadOptions` đối tượng và thiết lập`PreferredControlType`tài sản để`HtmlControlType.StructuredDocumentTag`. Điều này yêu cầu Aspose.Words sử dụng StructuredDocumentTags để thể hiện HTML khi tải.

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## Bước 3: Tải và lưu tài liệu

 Chúng tôi sử dụng`Document` lớp để tải mã HTML từ luồng bộ nhớ với các tùy chọn tải được xác định trước đó. Sau đó, chúng tôi lưu tài liệu vào thư mục được chỉ định với`.docx`định dạng tập tin.

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### Mã nguồn ví dụ cho loại điều khiển ưa thích với Aspose.Words for .NET

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

Đó là tất cả ! Bạn đã chỉ định thành công loại điều khiển ưa thích khi tải tài liệu HTML bằng Aspose.Words cho .NET.

## Phần kết luận

 Bằng cách làm theo hướng dẫn từng bước này, bạn đã học cách sử dụng tính năng "Loại điều khiển ưa thích" trong Aspose.Words cho .NET để chỉ định loại điều khiển mong muốn khi tải tài liệu HTML. Thiết lập`PreferredControlType`tài sản để`HtmlControlType.StructuredDocumentTag` cho phép Aspose.Words sử dụng StructuredDocumentTags (SDT) để trình bày và xử lý nội dung HTML tốt hơn. Bạn cũng có thể khám phá các loại điều khiển khác để phù hợp với yêu cầu cụ thể của mình. Sử dụng tính năng này giúp đảm bảo xử lý chính xác và hiệu quả các tài liệu HTML trong ứng dụng C# của bạn bằng Aspose.Words.

### Câu hỏi thường gặp về loại điều khiển ưa thích trong tài liệu word

#### Câu hỏi: Tính năng "Loại điều khiển ưa thích" trong Aspose.Words dành cho .NET là gì?

Trả lời: Tính năng "Loại điều khiển ưa thích" cho phép bạn chỉ định loại điều khiển ưa thích để thể hiện các phần tử HTML khi tải tài liệu HTML. Nó giúp chọn loại điều khiển thích hợp để thể hiện và xử lý nội dung HTML tốt hơn.

#### Câu hỏi: Làm cách nào để đặt loại điều khiển ưa thích khi tải tài liệu HTML?

 Trả lời: Để đặt loại điều khiển ưa thích, bạn cần tạo một`HtmlLoadOptions` đối tượng và thiết lập nó`PreferredControlType` tài sản theo ý muốn`HtmlControlType` . Trong ví dụ được cung cấp,`HtmlControlType.StructuredDocumentTag` Được sử dụng.

#### Câu hỏi: Tầm quan trọng của việc sử dụng Thẻ tài liệu có cấu trúc (SDT) làm loại điều khiển ưu tiên là gì?

Đáp: Thẻ tài liệu có cấu trúc (SDT) là các thành phần dựa trên XML có thể được sử dụng để thể hiện nội dung và điều khiển phức tạp trong tài liệu Word. Việc sử dụng SDT làm loại điều khiển ưu tiên có thể mang lại khả năng tương thích và trình bày nội dung HTML tốt hơn.

#### Câu hỏi: Làm cách nào tôi có thể đảm bảo rằng Aspose.Words sử dụng loại điều khiển ưa thích khi tải tài liệu HTML?

 A: Bằng cách thiết lập`PreferredControlType`tài sản để`HtmlControlType.StructuredDocumentTag`như được hiển thị trong mã nguồn ví dụ, Aspose.Words sẽ sử dụng SDT để thể hiện các phần tử HTML khi tải tài liệu.

#### Câu hỏi: Tôi có thể sử dụng các loại điều khiển khác làm tùy chọn ưu tiên không?

 Đ: Vâng, ngoài`HtmlControlType.StructuredDocumentTag` , Aspose.Words for .NET hỗ trợ các loại điều khiển khác như`HtmlControlType.ContentControl` Và`HtmlControlType.CustomXmlMarkup`.