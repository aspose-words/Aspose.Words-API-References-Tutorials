---
title: Phạm vi thẻ tài liệu có cấu trúc Bắt đầu ánh xạ Xml
linktitle: Phạm vi thẻ tài liệu có cấu trúc Bắt đầu ánh xạ Xml
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách liên kết động dữ liệu XML với các thẻ tài liệu có cấu trúc trong Word bằng Aspose.Words cho .NET. Thực hiện theo hướng dẫn từng bước của chúng tôi.
type: docs
weight: 10
url: /vi/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---
## Giới thiệu

Bạn đã bao giờ muốn chèn động dữ liệu XML vào tài liệu Word chưa? Vâng, bạn thật may mắn! Aspose.Words for .NET giúp công việc này trở nên dễ dàng. Trong hướng dẫn này, chúng ta sẽ đi sâu vào phạm vi thẻ tài liệu có cấu trúc để bắt đầu ánh xạ XML. Tính năng này cho phép bạn liên kết các phần XML tùy chỉnh với các điều khiển nội dung, đảm bảo nội dung tài liệu của bạn cập nhật liền mạch với dữ liệu XML của bạn. Sẵn sàng biến tài liệu của bạn thành những kiệt tác năng động.

## Điều kiện tiên quyết

Trước khi chuyển sang phần mã hóa, hãy đảm bảo bạn có mọi thứ mình cần:

1.  Aspose.Words for .NET Library: Đảm bảo bạn có phiên bản mới nhất. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/words/net/).
2. Môi trường phát triển: Visual Studio hoặc bất kỳ IDE nào khác hỗ trợ C#.
3. Kiến thức cơ bản về C#: Bắt buộc phải làm quen với lập trình C#.
4. Tài liệu Word: Một tài liệu Word mẫu để làm việc.

## Nhập không gian tên

Trước tiên, hãy nhập các không gian tên cần thiết. Điều này sẽ đảm bảo chúng tôi có quyền truy cập vào tất cả các lớp và phương thức cần thiết trong Aspose.Words cho .NET.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Markup;
using System.Text;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Mọi dự án đều cần có nền tảng, phải không? Ở đây, chúng tôi thiết lập đường dẫn đến thư mục tài liệu của bạn.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tải tài liệu Word

Tiếp theo, chúng ta tải tài liệu Word. Đây là tài liệu mà chúng ta sẽ chèn dữ liệu XML của mình.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
```

## Bước 3: Thêm phần XML tùy chỉnh

Chúng ta cần xây dựng một phần XML chứa dữ liệu mà chúng ta muốn chèn và thêm nó vào bộ sưu tập CustomXmlPart của tài liệu. Phần XML tùy chỉnh này sẽ đóng vai trò là nguồn dữ liệu cho các thẻ tài liệu có cấu trúc của chúng tôi.

### Tạo một phần XML

Đầu tiên, tạo một ID duy nhất cho phần XML và xác định nội dung của nó.

```csharp
// Xây dựng một phần XML chứa dữ liệu và thêm nó vào bộ sưu tập CustomXmlPart của tài liệu.
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

### Xác minh nội dung phần XML

Để đảm bảo phần XML được thêm chính xác, chúng tôi in nội dung của nó.

```csharp
Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
```

## Bước 4: Tạo thẻ tài liệu có cấu trúc

Thẻ tài liệu có cấu trúc (SDT) là một điều khiển nội dung có thể liên kết với một phần XML. Ở đây, chúng tôi tạo một SDT sẽ hiển thị nội dung của phần XML tùy chỉnh của chúng tôi.

Đầu tiên, xác định vị trí bắt đầu phạm vi SDT trong tài liệu.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
```

## Bước 5: Đặt ánh xạ XML cho SDT

Bây giờ là lúc liên kết phần XML của chúng ta với SDT. Bằng cách thiết lập ánh xạ XML, chúng tôi chỉ định phần nào của dữ liệu XML sẽ được hiển thị trong SDT.

 XPath trỏ tới phần tử cụ thể trong phần XML mà chúng ta muốn hiển thị. Ở đây, chúng tôi đề cập đến điều thứ hai`<text>` phần tử bên trong`<root>` yếu tố.

```csharp
// Đặt ánh xạ cho Thẻ tài liệu có cấu trúc của chúng tôi
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Bước 6: Lưu tài liệu

Cuối cùng, lưu tài liệu để xem những thay đổi đang diễn ra. SDT trong tài liệu Word bây giờ sẽ hiển thị nội dung XML được chỉ định.

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Phần kết luận

Và bạn có nó! Bạn đã ánh xạ thành công một phần XML tới thẻ tài liệu có cấu trúc trong tài liệu Word bằng Aspose.Words cho .NET. Tính năng mạnh mẽ này cho phép bạn tạo các tài liệu động và dựa trên dữ liệu một cách dễ dàng. Cho dù bạn đang tạo báo cáo, hóa đơn hay bất kỳ loại tài liệu nào khác, ánh xạ XML có thể hợp lý hóa đáng kể quy trình làm việc của bạn.

## Câu hỏi thường gặp

### Thẻ tài liệu có cấu trúc trong Word là gì?
Thẻ tài liệu có cấu trúc, còn được gọi là điều khiển nội dung, là nơi chứa các loại nội dung cụ thể trong tài liệu Word. Chúng có thể được sử dụng để liên kết dữ liệu, hạn chế chỉnh sửa hoặc hướng dẫn người dùng tạo tài liệu.

### Làm cách nào tôi có thể cập nhật nội dung phần XML một cách linh hoạt?
 Bạn có thể cập nhật nội dung phần XML bằng cách sửa đổi`xmlPartContent` chuỗi trước khi thêm nó vào tài liệu. Chỉ cần cập nhật chuỗi với dữ liệu mới và thêm nó vào`CustomXmlParts` bộ sưu tập.

### Tôi có thể liên kết nhiều phần XML với các SDT khác nhau trong cùng một tài liệu không?
Có, bạn có thể liên kết nhiều phần XML với các SDT khác nhau trong cùng một tài liệu. Mỗi SDT có thể có phần XML riêng và ánh xạ XPath.

### Có thể ánh xạ các cấu trúc XML phức tạp tới SDT không?
Tuyệt đối! Bạn có thể ánh xạ các cấu trúc XML phức tạp tới SDT bằng cách sử dụng các biểu thức XPath chi tiết trỏ chính xác đến các phần tử mong muốn trong phần XML.

### Làm cách nào để xóa phần XML khỏi tài liệu?
 Bạn có thể xóa một phần XML bằng cách gọi`Remove` phương pháp trên`CustomXmlParts` thu thập, chuyển giao`xmlPartId` của phần XML bạn muốn xóa.