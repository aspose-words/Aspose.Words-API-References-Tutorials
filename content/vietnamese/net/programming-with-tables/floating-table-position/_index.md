---
title: Vị trí bàn nổi
linktitle: Vị trí bàn nổi
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách định vị bảng ở vị trí nổi trong tài liệu Word bằng Aspose.Words cho .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/floating-table-position/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách sử dụng Aspose.Words cho .NET để định vị bảng ở vị trí nổi trong tài liệu Word. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Khi kết thúc hướng dẫn này, bạn sẽ có thể kiểm soát vị trí và căn chỉnh của các bảng nổi trong tài liệu Word của mình theo chương trình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Load tài liệu và truy cập vào bảng
Để bắt đầu Xử lý từ bằng bảng, chúng ta cần tải tài liệu chứa nó và truy cập nó. Thực hiện theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Truy cập vào mảng
Table table = doc.FirstSection.Body.Tables[0];
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn. Ngoài ra, hãy đảm bảo tài liệu chứa một bảng sẽ được đặt ở vị trí nổi.

## Bước 3: Định vị tấm nổi
Tiếp theo, chúng ta sẽ đặt bảng ở vị trí nổi bằng cách sử dụng các thuộc tính do Aspose.Words cung cấp cho .NET. Sử dụng mã sau đây:

```csharp
// Định vị bàn nổi
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Ở đây chúng tôi sử dụng`AbsoluteHorizontalDistance` Thuộc tính để đặt khoảng cách ngang tuyệt đối của bảng từ cạnh trái của trang. Chúng tôi cũng sử dụng`RelativeVerticalAlignment` thuộc tính để đặt căn chỉnh theo chiều dọc tương đối của bảng với nội dung xung quanh.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với bảng được đặt ở vị trí nổi. Sử dụng mã sau đây:

```csharp
// Lưu tài liệu đã sửa đổi
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Vị trí bảng nổi bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã học cách định vị bảng ở vị trí nổi trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể kiểm soát vị trí và căn chỉnh các bảng nổi trong tài liệu Word của mình theo chương trình.