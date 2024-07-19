---
title: Tạo phần lặp lại bảng được ánh xạ tới phần Xml tùy chỉnh
linktitle: Tạo phần lặp lại bảng được ánh xạ tới phần Xml tùy chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo bảng có phần lặp lại được ánh xạ tới CustomXmlPart trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Hướng dẫn này trình bày cách tạo bảng có phần lặp lại được ánh xạ tới Phần Xml tùy chỉnh trong tài liệu Word bằng Aspose.Words cho .NET. Phần lặp lại cho phép bạn thêm động các hàng dựa trên dữ liệu XML được lưu trữ trong Phần Xml tùy chỉnh.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"`với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu và DocumentBuilder
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` để xây dựng nội dung của tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Thêm dữ liệu XML tùy chỉnh vào CustomXmlPart
 Tạo một`CustomXmlPart` và thêm dữ liệu XML tùy chỉnh vào đó. Trong ví dụ này, chúng tôi tạo một chuỗi XML đại diện cho một bộ sưu tập sách có tên và tác giả.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Bước 4: Tạo bảng và cấu trúc bảng
 Bắt đầu tạo bảng bằng cách sử dụng`StartTable` phương pháp của`DocumentBuilder` . Thêm ô và nội dung bảng bằng cách sử dụng`InsertCell`Và`Write` phương pháp.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Bước 5: Tạo phần lặp lại được ánh xạ tới XML tùy chỉnh
 Tạo một`StructuredDocumentTag` với`SdtType.RepeatingSection` để đại diện cho phần lặp lại. Đặt ánh xạ XML cho phần lặp lại bằng cách sử dụng`SetMapping` phương pháp của`XmlMapping` tài sản. Trong ví dụ này, chúng tôi ánh xạ phần lặp lại tới`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Bước 6: Tạo mục phần lặp lại và thêm ô
 Tạo một`StructuredDocumentTag` với`SdtType.RepeatingSectionItem` để đại diện cho mục phần lặp lại. Nối nó khi còn nhỏ vào phần lặp lại.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Tạo một`Row` để thể hiện từng mục trong phần lặp lại và nối nó vào mục phần lặp lại.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Bước 7: Thêm điều khiển nội dung trong phần lặp lại
 Tạo nên`StructuredDocumentTag` đồ vật có`SdtType.PlainText`

  để thể hiện các điều khiển tiêu đề và nội dung tác giả. Đặt ánh xạ XML cho từng điều khiển nội dung bằng cách sử dụng`SetMapping` phương pháp của`XmlMapping` tài sản. Trong ví dụ này, chúng tôi ánh xạ điều khiển tiêu đề tới`/books[1]/book[1]/title[1]` và tác giả kiểm soát`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Bước 8: Lưu tài liệu
 Lưu tài liệu đã sửa đổi vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Mã nguồn ví dụ để tạo phần lặp lại bảng được ánh xạ tới phần Xml tùy chỉnh bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Đó là nó! Bạn đã tạo thành công một bảng có phần lặp lại được ánh xạ tới CustomXmlPart trong tài liệu Word của bạn bằng Aspose.Words cho .NET.