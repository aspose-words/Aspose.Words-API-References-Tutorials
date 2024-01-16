---
title: Tự động điều chỉnh theo chiều rộng trang
linktitle: Tự động điều chỉnh theo chiều rộng trang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tự động điều chỉnh bảng theo chiều rộng trang trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/auto-fit-to-page-width/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Words cho .NET để tự động điều chỉnh bảng theo chiều rộng trang trong tài liệu Word. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể thao tác các bảng trong tài liệu Word theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tạo và cấu hình tài liệu
Để bắt đầu Xử lý từ bằng bảng, chúng ta cần tạo một tài liệu và định cấu hình trình tạo tài liệu. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và trình tạo tài liệu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Chèn và cấu hình bảng
Tiếp theo, chúng ta sẽ chèn một bảng vào tài liệu với chiều rộng chiếm một nửa chiều rộng của trang. Sử dụng mã sau đây:

```csharp
// Chèn bảng và định cấu hình chiều rộng của nó
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Ở đây, chúng tôi sử dụng trình tạo tài liệu để bắt đầu tạo bảng, chèn ô và đặt chiều rộng ưa thích của bảng thành 50% chiều rộng trang. Sau đó, chúng tôi thêm văn bản vào mỗi ô.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với bảng được điều chỉnh theo chiều rộng của trang. Sử dụng mã sau đây:

```csharp
// Lưu tài liệu đã sửa đổi
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.
  
### Mã nguồn mẫu cho tính năng Tự động điều chỉnh độ rộng trang bằng Aspose.Words for .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Chèn một bảng có chiều rộng chiếm một nửa chiều rộng của trang.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách tự động điều chỉnh bảng theo chiều rộng trang trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể thao tác các bảng trong tài liệu Word theo chương trình. Tính năng này cho phép bạn điều chỉnh linh hoạt độ rộng của bảng theo trang, từ đó mang lại một tài liệu chuyên nghiệp và hấp dẫn về mặt hình ảnh.