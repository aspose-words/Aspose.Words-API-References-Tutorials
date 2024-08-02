---
title: Tạo phần lặp lại bảng được ánh xạ tới phần Xml tùy chỉnh
linktitle: Tạo phần lặp lại bảng được ánh xạ tới phần Xml tùy chỉnh
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo bảng có phần lặp lại được ánh xạ tới CustomXmlPart trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---
## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình tạo bảng có phần lặp lại được ánh xạ tới phần XML tùy chỉnh bằng cách sử dụng Aspose.Words cho .NET. Điều này đặc biệt hữu ích để tạo tài liệu động dựa trên dữ liệu có cấu trúc.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:
1.  Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải nó xuống từ[trang web giả định](https://releases.aspose.com/words/net/).
2. Hiểu biết cơ bản về C# và XML.

## Nhập không gian tên

Đảm bảo bao gồm các không gian tên cần thiết trong dự án của bạn:

```csharp
using Aspose.Words;
using Aspose.Words.Markup;
using Aspose.Words.Tables;
```

## Bước 1: Khởi tạo Document và DocumentBuilder

 Đầu tiên, tạo một tài liệu mới và khởi tạo một`DocumentBuilder`:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 2: Thêm phần XML tùy chỉnh

Thêm phần XML tùy chỉnh vào tài liệu. XML này chứa dữ liệu chúng tôi muốn ánh xạ tới bảng của mình:

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
    "<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
    "<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
    "<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Bước 3: Tạo cấu trúc bảng

 Tiếp theo, sử dụng`DocumentBuilder` để tạo tiêu đề bảng:

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Bước 4: Tạo phần lặp lại

 Tạo một`StructuredDocumentTag` (SDT) cho phần lặp lại và ánh xạ nó tới dữ liệu XML:

```csharp
StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Bước 5: Tạo mục phần lặp lại

Tạo SDT cho mục phần lặp lại và thêm nó vào phần lặp lại:

```csharp
StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Bước 6: Ánh xạ dữ liệu XML tới các ô trong bảng

Tạo SDT cho tiêu đề và tác giả, ánh xạ chúng tới dữ liệu XML và nối chúng vào hàng:

```csharp
StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Bước 7: Lưu tài liệu

Cuối cùng, lưu tài liệu vào thư mục được chỉ định:

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

## Phần kết luận

Bằng cách làm theo các bước này, bạn đã tạo thành công một bảng có phần lặp lại được ánh xạ tới phần XML tùy chỉnh bằng cách sử dụng Aspose.Words cho .NET. Điều này cho phép tạo nội dung động dựa trên dữ liệu có cấu trúc, giúp việc tạo tài liệu trở nên linh hoạt và mạnh mẽ hơn.

## Câu hỏi thường gặp

### Thẻ tài liệu có cấu trúc (SDT) là gì?
SDT, còn được gọi là kiểm soát nội dung, là vùng giới hạn trong tài liệu được sử dụng để chứa dữ liệu có cấu trúc.

### Tôi có thể sử dụng các kiểu dữ liệu khác trong phần XML tùy chỉnh không?
Có, bạn có thể cấu trúc phần XML tùy chỉnh của mình với bất kỳ loại dữ liệu nào và ánh xạ chúng cho phù hợp.

### Làm cách nào để thêm nhiều hàng hơn vào phần lặp lại?
Phần lặp lại tự động sao chép cấu trúc hàng cho từng mục trong đường dẫn XML được ánh xạ.