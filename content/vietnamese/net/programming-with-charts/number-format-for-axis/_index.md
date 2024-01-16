---
title: Định dạng số cho trục trong biểu đồ
linktitle: Định dạng số cho trục trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách đặt định dạng số cho một trục trong biểu đồ bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/number-format-for-axis/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để đặt định dạng số cho một trục trong biểu đồ. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, thêm dữ liệu chuỗi và định dạng nhãn trục.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

- Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải xuống bằng cách sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu đầu ra sẽ được lưu.

## Bước 2: Tạo một tài liệu mới và chèn biểu đồ

 Tạo một cái mới`Document` đối tượng và một`DocumentBuilder` để xây dựng tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tiếp theo, sử dụng`InsertChart` phương pháp của`DocumentBuilder` để chèn biểu đồ cột vào tài liệu.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Thêm dữ liệu chuỗi vào biểu đồ

Thêm dữ liệu chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm năm mục có giá trị tương ứng.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## Bước 4: Định dạng nhãn trục

 Để đặt định dạng số cho nhãn trục Y, hãy truy cập vào`AxisY` thuộc tính của biểu đồ và thiết lập`NumberFormat.FormatCode` thuộc tính sang định dạng mong muốn. Trong ví dụ này, chúng tôi đặt định dạng thành "#,##0" để hiển thị các số có dấu phân cách hàng nghìn.

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## Bước 5: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

Điều này hoàn tất việc thực hiện cài đặt định dạng số cho trục bằng Aspose.Words for .NET.

### Mã nguồn mẫu cho Định dạng số cho trục sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách đặt định dạng số cho một trục trong biểu đồ bằng Aspose.Words for .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo tài liệu mới, chèn biểu đồ cột, thêm dữ liệu chuỗi và định dạng nhãn trục để hiển thị số ở định dạng cụ thể.

Aspose.Words for .NET cung cấp các tính năng mạnh mẽ để tùy chỉnh giao diện của biểu đồ trong tài liệu Word. Bằng cách đặt định dạng số cho nhãn trục, bạn có thể kiểm soát cách hiển thị số, bao gồm các tùy chọn như vị trí thập phân, dấu phân cách hàng nghìn, ký hiệu tiền tệ, v.v. Điều này cho phép bạn trình bày dữ liệu số một cách rõ ràng và có ý nghĩa.

Với Aspose.Words for .NET, bạn có thể linh hoạt định dạng các khía cạnh khác nhau của biểu đồ, bao gồm cả nhãn trục. Bằng cách đặt định dạng số cho trục, bạn có thể đảm bảo tính nhất quán và cải thiện khả năng đọc của biểu đồ, giúp người dùng diễn giải các giá trị được biểu thị dễ dàng hơn.

### Câu hỏi thường gặp

#### Q1. Định dạng số cho một trục trong biểu đồ là gì?
Định dạng số cho một trục trong biểu đồ đề cập đến định dạng được áp dụng cho các giá trị số được hiển thị trên trục. Nó cho phép bạn kiểm soát cách trình bày các số, bao gồm các tùy chọn như vị trí thập phân, dấu phân cách hàng nghìn, ký hiệu tiền tệ, ký hiệu phần trăm, v.v. Bằng cách đặt định dạng số, bạn có thể tùy chỉnh giao diện của dữ liệu số trong biểu đồ cho phù hợp với yêu cầu cụ thể của mình.

#### Q2. Làm cách nào để đặt định dạng số cho nhãn trục?
 Để đặt định dạng số cho nhãn trục trong biểu đồ bằng Aspose.Words cho .NET, bạn có thể truy cập vào`AxisY` thuộc tính của biểu đồ và thiết lập`NumberFormat.FormatCode`thuộc tính thành mã định dạng mong muốn. Mã định dạng tuân theo cú pháp của các mẫu định dạng số tiêu chuẩn và xác định cách hiển thị các số. Ví dụ: bạn có thể sử dụng "#,##0,00" để hiển thị các số có hai chữ số thập phân và dấu phân cách hàng nghìn.

#### Q3. Tôi có thể đặt các định dạng số khác nhau cho nhãn trục X và trục Y không?
Có, bạn có thể đặt các định dạng số khác nhau cho nhãn trục X và trục Y bằng Aspose.Words for .NET. Truy cập trục tương ứng (`AxisX` cho trục X hoặc`AxisY` cho trục Y) của biểu đồ và sửa đổi`NumberFormat.FormatCode` thuộc tính riêng cho từng trục. Điều này cho phép bạn áp dụng các định dạng số khác nhau cho nhãn trên mỗi trục dựa trên yêu cầu cụ thể của bạn.

#### Q4. Một số mã định dạng số phổ biến tôi có thể sử dụng là gì?
Aspose.Words for .NET hỗ trợ nhiều mã định dạng số mà bạn có thể sử dụng để định dạng nhãn trục trong biểu đồ. Một số mã định dạng phổ biến bao gồm:

- `0` hoặc`#` - Hiển thị số không có chữ số thập phân.
- `0.00` hoặc`#.00` - Hiển thị số có hai chữ số thập phân.
- `#,##0` Hiển thị số có dấu phân cách hàng nghìn.
- `"€"0.00` - Hiển thị số có ký hiệu tiền tệ Euro và hai chữ số thập phân.
- `"%"0` - Hiển thị số dưới dạng phần trăm.

 Bạn có thể tìm thêm thông tin về số[mã định dạng](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/) trong Tài liệu tham khảo API của Aspose.Words cho .NET.

#### Q5. Tôi có thể tùy chỉnh các thuộc tính khác của nhãn trục không?
Có, Aspose.Words for .NET cung cấp nhiều thuộc tính để tùy chỉnh giao diện và hoạt động của nhãn trục. Ngoài định dạng số, bạn có thể sửa đổi các thuộc tính như phông chữ, kích thước, màu sắc, hướng, căn chỉnh, v.v. Điều này cho phép bạn tùy chỉnh đầy đủ các nhãn trục để phù hợp với yêu cầu về phong cách và cách trình bày mà bạn mong muốn.