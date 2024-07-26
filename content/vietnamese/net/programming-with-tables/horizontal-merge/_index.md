---
title: Hợp nhất theo chiều ngang
linktitle: Hợp nhất theo chiều ngang
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách hợp nhất các ô theo chiều ngang trong bảng Word với Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/horizontal-merge/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách hợp nhất các ô theo chiều ngang trong bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể hợp nhất các ô theo chiều ngang trong bảng Word theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tạo tài liệu và khởi tạo trình tạo tài liệu
Để bắt đầu Xử lý Từ với bảng và ô, chúng ta cần tạo một tài liệu mới và khởi tạo trình tạo tài liệu. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Tạo tài liệu và khởi tạo trình tạo tài liệu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Xây dựng bảng gộp ô theo chiều ngang
Tiếp theo, chúng ta sẽ xây dựng bảng và áp dụng tính năng hợp nhất ô theo chiều ngang bằng cách sử dụng các thuộc tính do Aspose.Words cung cấp cho .NET. Sử dụng mã sau đây:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Ô này được hợp nhất với ô trước đó và phải trống.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Ở đây chúng tôi sử dụng trình tạo tài liệu để xây dựng bảng và đặt thuộc tính hợp nhất ô theo chiều ngang. Chúng tôi sử dụng`HorizontalMerge` tài sản của`CellFormat` đối tượng để chỉ định kiểu hợp nhất theo chiều ngang để áp dụng cho từng ô. sử dụng`CellMerge.First` chúng tôi hợp nhất ô đầu tiên với ô tiếp theo, trong khi sử dụng`CellMerge.Previous` chúng ta hợp nhất ô hiện tại với ô trước đó.`CellMerge.None` chỉ ra rằng ô không nên được hợp nhất.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với các ô được hợp nhất theo chiều ngang. Sử dụng mã sau đây:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Hợp nhất ngang bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Ô này được hợp nhất với ô trước đó và phải trống.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách hợp nhất các ô theo chiều ngang trong một bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể áp dụng tính năng hợp nhất ô ngang trong bảng Word theo chương trình. Tính năng này cho phép bạn tạo bố cục bảng phức tạp hơn và sắp xếp dữ liệu của bạn tốt hơn.