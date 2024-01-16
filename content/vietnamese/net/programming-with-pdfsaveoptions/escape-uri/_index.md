---
title: Thoát URI trong tài liệu PDF
linktitle: Thoát URI trong tài liệu PDF
second_title: API xử lý tài liệu Aspose.Words
description: Hướng dẫn từng bước Cách thoát URI trong tài liệu PDF bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-pdfsaveoptions/escape-uri/
---

Bài viết này cung cấp hướng dẫn từng bước về cách Thoát URI trong Tài liệu PDF bằng Aspose.Words cho .NET. Chúng tôi sẽ giải thích chi tiết từng phần của mã. Khi kết thúc hướng dẫn này, bạn sẽ có thể hiểu cách chèn siêu liên kết bằng Uri thoát trong tài liệu.

Trước khi bắt đầu, hãy đảm bảo bạn đã cài đặt và định cấu hình thư viện Aspose.Words cho .NET trong dự án của mình. Bạn có thể tìm thấy thư viện và hướng dẫn cài đặt trên trang web Aspose.

## Bước 1: Xác định thư mục tài liệu

 Để bắt đầu, bạn cần xác định đường dẫn đến thư mục chứa tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục tài liệu của bạn.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo tài liệu và DocumentBuilder

 Tiếp theo chúng ta cần tạo mới`Document` đối tượng và một`DocumentBuilder` đối tượng để xây dựng tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn siêu liên kết có Uri thoát

 Sử dụng`InsertHyperlink` phương pháp của`DocumentBuilder` đối tượng để chèn siêu liên kết vào tài liệu. Uri phải được thoát bằng cách sử dụng`Uri.EscapeUriString` để tránh lỗi định dạng.

```csharp
builder.InsertHyperlink("Testlink",
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), sai);
builder. Writen();
builder.InsertHyperlink(Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"),
     Uri.EscapeUriString("https://www.google.com/search?q=%2Fthe%20test"), sai);
```

## Bước 4: Lưu tài liệu dưới dạng PDF

 Cuối cùng, chúng ta có thể lưu tài liệu dưới dạng PDF bằng cách sử dụng`Save` phương pháp của`Document` sự vật. Chỉ định tên tập tin đầu ra.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");
```

Đó là tất cả ! Bạn đã chèn thành công các siêu liên kết có Uri thoát vào tài liệu bằng Aspose.Words for .NET.

### Mã nguồn mẫu để thoát Uri bằng Aspose.Words cho .NET


```csharp

	// Đường dẫn đến thư mục tài liệu.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.InsertHyperlink("Testlink", 
		"https://www.google.com/search?q=%2Fthe%20test", sai);
	builder.Writeln();
	builder.InsertHyperlink("https:// www.google.com/search?q=%2Fthe%20test",
		"https://www.google.com/search?q=%2Fthe%20test", sai);

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.EscapeUri.pdf");    
  
```

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã trình bày cách thoát URI trong tài liệu PDF bằng Aspose.Words cho .NET. Bằng cách thoát URI, bạn có thể tránh các lỗi định dạng và đảm bảo rằng các siêu liên kết được diễn giải và hiển thị chính xác trong tài liệu PDF. Thực hiện theo các bước được nêu để chèn siêu liên kết có URI thoát vào tài liệu PDF của bạn. Hãy chắc chắn để trốn thoát.

### Các câu hỏi thường gặp

#### Câu hỏi: URI thoát trong tài liệu PDF là gì và tại sao nó lại quan trọng?
Trả lời: URI thoát trong tài liệu PDF đề cập đến phương pháp chuyển đổi các ký tự đặc biệt trong URL thành chuỗi thoát để tránh lỗi định dạng. Điều này rất quan trọng vì các ký tự đặc biệt trong URL có thể phá vỡ cấu trúc của URL và dẫn đến hiểu sai hoặc hiển thị không chính xác. Bằng cách thoát khỏi các ký tự đặc biệt, chúng tôi đảm bảo rằng URL được diễn giải và hiển thị chính xác trong tài liệu PDF.

#### Câu hỏi: Làm cách nào tôi có thể sử dụng Aspose.Words cho .NET để thoát URI trong tài liệu PDF?
Trả lời: Để thoát URI trong tài liệu PDF bằng Aspose.Words cho .NET, hãy làm theo các bước sau:

 Đặt đường dẫn thư mục nơi chứa tài liệu của bạn bằng cách thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế của thư mục tài liệu của bạn.

 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder` đối tượng để xây dựng tài liệu.

 Sử dụng`InsertHyperlink` phương pháp của`DocumentBuilder` đối tượng để chèn siêu liên kết vào tài liệu. Hãy chắc chắn thoát khỏi URI bằng cách sử dụng`Uri.EscapeUriString` để tránh lỗi định dạng.

 Sử dụng`Save` phương pháp của`Document` đối tượng lưu tài liệu ở định dạng PDF bằng cách chỉ định tên của tệp đầu ra.

#### Câu hỏi: Lợi ích của việc thoát URI trong tài liệu PDF là gì?
Đáp: Lợi ích của việc thoát URI trong tài liệu PDF là:

Ngăn ngừa lỗi định dạng: Tính năng thoát URI giúp ngăn ngừa lỗi định dạng do các ký tự đặc biệt trong một URL gây ra, đảm bảo rằng URL được diễn giải và hiển thị chính xác trong tài liệu PDF.

Khả năng tương thích với trình đọc PDF: URI thoát thường được trình đọc PDF hỗ trợ tốt, đảm bảo khả năng tương thích tốt hơn và trải nghiệm người dùng nhất quán.

#### Câu hỏi: Những ký tự đặc biệt nào nên được thoát trong URI?
 Đáp: Các ký tự đặc biệt phải được thoát trong URI là: dấu cách, <, >, ", #, %, {, },|, \, ^, ~, [, ], `, ;, /, ?, :, @, =, &, $, +, ,, [, ], and !.