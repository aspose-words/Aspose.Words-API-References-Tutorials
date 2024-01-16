---
title: Chèn bảng từ Html
linktitle: Chèn bảng từ Html
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách chèn bảng từ HTML vào tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/insert-table-from-html/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách chèn bảng vào tài liệu Word từ HTML bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể chèn các bảng từ HTML vào tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tạo tài liệu và khởi tạo trình tạo tài liệu
Để bắt đầu Xử lý Từ bằng trình tạo tài liệu và tài liệu, hãy làm theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu
Document doc = new Document();

// Khởi tạo trình tạo tài liệu
DocumentBuilder builder = new DocumentBuilder(doc);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Chèn bảng từ HTML
Tiếp theo, chúng ta sẽ chèn bảng vào tài liệu bằng mã HTML. Sử dụng mã sau đây:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Ở đây chúng tôi sử dụng`InsertHtml` phương pháp của trình tạo tài liệu để chèn HTML chứa bảng. HTML được chỉ định sẽ tạo một bảng có hai hàng và hai ô trong mỗi hàng. Bạn có thể tùy chỉnh nội dung của bảng bằng cách sửa đổi mã HTML theo nhu cầu của mình.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với bảng được chèn từ HTML. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Chèn bảng từ Html bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Lưu ý rằng AutoFitSettings không áp dụng cho các bảng được chèn từ HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách chèn bảng vào tài liệu Word từ HTML bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể chèn bảng từ HTML vào tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn chuyển đổi và nhập dữ liệu dạng bảng từ nguồn HTML vào tài liệu Word của mình.
