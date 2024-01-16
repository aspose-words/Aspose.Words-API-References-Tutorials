---
title: Liên kết SDT với phần Xml tùy chỉnh
linktitle: Liên kết SDT với phần Xml tùy chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách liên kết SDT với Phần Xml tùy chỉnh bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Hướng dẫn này trình bày cách liên kết Thẻ tài liệu có cấu trúc (SDT) với Phần Xml tùy chỉnh bằng cách sử dụng Aspose.Words cho .NET. SDT cho phép bạn thêm các điều khiển nội dung có cấu trúc vào tài liệu Word và CustomXmlParts cung cấp cách lưu trữ dữ liệu XML tùy chỉnh được liên kết với tài liệu.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và XML.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu và CustomXmlPart
 Tạo một phiên bản mới của`Document` lớp học và một`CustomXmlPart` để lưu trữ dữ liệu XML tùy chỉnh. XML tùy chỉnh phải ở định dạng XML hợp lệ. Trong ví dụ này, chúng tôi sử dụng một chuỗi XML đơn giản`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Bước 3: Thêm Thẻ tài liệu có cấu trúc (SDT) vào tài liệu
 Thêm một`StructuredDocumentTag` vào tài liệu để đóng vai trò kiểm soát nội dung. Chỉ định la`SdtType` BẰNG`PlainText` và`MarkupLevel` BẰNG`Block` để tạo SDT cấp khối.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Bước 4: Đặt ánh xạ XML cho SDT
 Ánh xạ SDT tới`CustomXmlPart` bằng cách sử dụng`SetMapping` phương pháp của`XmlMapping` tài sản. Chỉ định la`CustomXmlPart` , biểu thức XPath để định vị nút XML mong muốn và tiền tố vùng tên nếu cần. Trong ví dụ này, chúng tôi ánh xạ SDT tới`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Bước 5: Lưu tài liệu
 Lưu tài liệu đã sửa đổi vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Mã nguồn ví dụ cho Bind Sd Tto Custom Xml Part sử dụng Aspose.Words for .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Đó là nó! Bạn đã liên kết thành công SDT với CustomXmlPart trong tài liệu Word của mình bằng Aspose.Words for .NET.