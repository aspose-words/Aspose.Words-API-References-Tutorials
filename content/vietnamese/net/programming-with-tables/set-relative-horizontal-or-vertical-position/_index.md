---
title: Đặt vị trí ngang hoặc dọc tương đối
linktitle: Đặt vị trí ngang hoặc dọc tương đối
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt vị trí ngang hoặc dọc tương đối của bảng trong tài liệu Word bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

Trong hướng dẫn này, chúng ta sẽ tìm hiểu cách đặt vị trí ngang hoặc dọc tương đối của bảng trong tài liệu Word bằng Aspose.Words cho .NET. Chúng tôi sẽ làm theo hướng dẫn từng bước để hiểu mã và triển khai tính năng này. Đến cuối hướng dẫn này, bạn sẽ có thể đặt vị trí ngang hoặc dọc tương đối của bảng trong tài liệu Word của mình.

## Bước 1: Thiết lập dự án
1. Khởi chạy Visual Studio và tạo một dự án C# mới.
2. Thêm tham chiếu đến thư viện Aspose.Words for .NET.

## Bước 2: Tải tài liệu
Để bắt đầu Xử lý văn bản với tài liệu, hãy làm theo các bước sau:

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Tải tài liệu
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Đảm bảo thay thế "THƯ MỤC TÀI LIỆU CỦA BẠN" bằng đường dẫn thực tế đến thư mục tài liệu của bạn và cung cấp tên tệp chính xác.

## Bước 3: Thiết lập vị trí tương đối của bảng
Tiếp theo, chúng ta sẽ đặt vị trí ngang hoặc dọc tương đối của bảng. Sử dụng mã sau đây:

```csharp
// Truy xuất bảng
Table table = doc.FirstSection.Body.Tables[0];

//Định nghĩa vị trí nằm ngang tương đối của bàn
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

// Xác định vị trí thẳng đứng tương đối của bảng
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

 Ở đây chúng tôi sử dụng tài liệu để truy xuất bảng đầu tiên từ phần nội dung của phần đầu tiên. Tiếp theo, chúng ta đặt vị trí nằm ngang tương đối của bảng bằng`HorizontalAnchor` tài sản bằng cách sử dụng`RelativeHorizontalPosition.Column` giá trị. Tương tự, chúng ta đặt vị trí thẳng đứng tương đối của bảng bằng`VerticalAnchor` tài sản bằng cách sử dụng`RelativeVerticalPosition.Page` giá trị.

## Bước 4: Lưu tài liệu đã sửa đổi
Cuối cùng, chúng ta cần lưu tài liệu đã sửa đổi với vị trí tương đối của bảng đã xác định. Sử dụng mã sau đây:

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

Đảm bảo chỉ định đúng đường dẫn và tên tệp cho tài liệu đầu ra.

### Mã nguồn mẫu cho Đặt vị trí ngang hoặc dọc tương đối bằng Aspose.Words cho .NET 

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## Phần kết luận
Trong hướng dẫn này, chúng ta đã tìm hiểu cách đặt vị trí ngang hoặc dọc tương đối của bảng trong tài liệu Word bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước này và triển khai mã C# được cung cấp, bạn có thể áp dụng vị trí tương đối này cho các bảng trong tài liệu Word của mình.