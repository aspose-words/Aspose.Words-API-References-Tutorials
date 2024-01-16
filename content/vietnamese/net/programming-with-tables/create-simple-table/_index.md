---
title: Tạo bảng đơn giản
linktitle: Tạo bảng đơn giản
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tạo bảng đơn giản trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/create-simple-table/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách tạo một bảng đơn giản trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể tạo các bảng tùy chỉnh trong tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tạo tài liệu và khởi tạo trình tạo tài liệu
Để bắt đầu xây dựng bảng, chúng ta cần tạo một tài liệu mới và khởi tạo trình tạo tài liệu. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tạo tài liệu và khởi tạo trình tạo tài liệu
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 3: Xây dựng mảng
Tiếp theo, chúng ta sẽ xây dựng bảng bằng các phương thức do trình tạo tài liệu cung cấp. Sử dụng mã sau đây:

```csharp
// Bắt đầu xây dựng mảng
builder. StartTable();

// Xây dựng ô đầu tiên của hàng đầu tiên
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Xây dựng ô thứ hai của hàng đầu tiên
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Gọi phương thức sau để kết thúc dòng đầu tiên và bắt đầu một dòng mới
builder. EndRow();

// Xây dựng ô đầu tiên của hàng thứ hai
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Xây dựng ô thứ hai của hàng thứ hai
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Gọi phương thức tiếp theo để kết thúc dòng thứ hai
builder. EndRow();

// Dấu hiệu cho thấy việc xây dựng bảng đã hoàn tất
builder. EndTable();
```

 Ở đây chúng tôi sử dụng trình tạo tài liệu để xây dựng bảng từng bước. Chúng tôi bắt đầu bằng cách gọi`StartTable()` để khởi tạo bảng, sau đó sử dụng`InsertCell()` để chèn ô và`Write()` để thêm nội dung vào từng ô. Chúng tôi cũng dùng`EndRow()` để kết thúc một hàng và bắt đầu một hàng mới. Cuối cùng, chúng tôi gọi`EndTable()` để chỉ ra rằng việc xây dựng bảng đã hoàn tất.

## Bước 4: Lưu tài liệu
Cuối cùng chúng ta cần lưu

  tài liệu với bảng đã tạo. Sử dụng mã sau đây:

```csharp
// Lưu tài liệu
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Tạo bảng đơn giản bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Bắt đầu xây dựng bảng.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Xây dựng ô thứ hai.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Gọi phương thức sau để kết thúc hàng và bắt đầu một hàng mới.
	builder.EndRow();
	// Xây dựng ô đầu tiên của hàng thứ hai.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Xây dựng ô thứ hai.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Báo hiệu chúng ta đã hoàn thành việc xây dựng bảng.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách tạo một bảng đơn giản trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể tạo các bảng tùy chỉnh trong tài liệu Word của mình theo chương trình. Tính năng này cho phép bạn định dạng và sắp xếp dữ liệu của mình một cách có cấu trúc và rõ ràng.