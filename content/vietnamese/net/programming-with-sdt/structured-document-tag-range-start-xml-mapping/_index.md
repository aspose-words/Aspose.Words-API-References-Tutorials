---
title: Phạm vi thẻ tài liệu có cấu trúc Bắt đầu ánh xạ Xml
linktitle: Phạm vi thẻ tài liệu có cấu trúc Bắt đầu ánh xạ Xml
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thiết lập ánh xạ XML cho phạm vi thẻ tài liệu có cấu trúc bắt đầu trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Hướng dẫn này giải thích cách thiết lập ánh xạ XML cho phạm vi thẻ tài liệu có cấu trúc bắt đầu trong tài liệu Word bằng Aspose.Words cho .NET. Ánh xạ XML cho phép bạn hiển thị các phần cụ thể của nguồn dữ liệu XML trong điều khiển nội dung.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục chứa tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu và tạo phần XML
 Tải tài liệu Word bằng cách sử dụng`Document` hàm tạo, chuyển đường dẫn đến tài liệu dưới dạng tham số. Tạo một phần XML chứa dữ liệu bạn muốn hiển thị trong thẻ tài liệu có cấu trúc.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Bước 3: Đặt ánh xạ XML cho thẻ tài liệu có cấu trúc
Truy xuất phạm vi thẻ tài liệu có cấu trúc bắt đầu từ tài liệu. Sau đó, đặt ánh xạ XML cho thẻ tài liệu có cấu trúc để hiển thị một phần cụ thể của phần XML tùy chỉnh bằng cách sử dụng biểu thức XPath.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Bước 4: Lưu tài liệu
 Lưu tài liệu đã sửa đổi vào thư mục được chỉ định bằng cách sử dụng`Save`phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Mã nguồn mẫu cho Phạm vi thẻ tài liệu có cấu trúc Bắt đầu ánh xạ Xml bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Xây dựng một phần XML chứa dữ liệu và thêm nó vào bộ sưu tập CustomXmlPart của tài liệu.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Tạo StructuredDocumentTag sẽ hiển thị nội dung của CustomXmlPart của chúng tôi trong tài liệu.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Nếu chúng tôi đặt ánh xạ cho Thẻ tài liệu có cấu trúc của mình,
	// nó sẽ chỉ hiển thị một phần của CustomXmlPart mà XPath trỏ tới.
	// XPath này sẽ trỏ đến phần tử "<text>" nội dung thứ hai của phần tử "<root>" đầu tiên của CustomXmlPart của chúng ta.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Đó là nó! Bạn đã thiết lập thành công ánh xạ XML cho phạm vi thẻ tài liệu có cấu trúc bắt đầu trong tài liệu Word của mình bằng cách sử dụng Aspose.Words for .NET.