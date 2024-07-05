---
title: Thêm giá trị ngày giờ vào trục của biểu đồ
linktitle: Thêm giá trị ngày giờ vào trục của biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách thêm giá trị ngày giờ vào trục của biểu đồ bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/date-time-values-to-axis/
---

Hướng dẫn này giải thích cách thêm các giá trị ngày giờ vào trục của biểu đồ bằng Aspose.Words for .NET.

## Điều kiện tiên quyết
Để làm theo hướng dẫn này, bạn cần có những điều sau:

- Đã cài đặt thư viện Aspose.Words cho .NET.
- Kiến thức cơ bản về C# và Xử lý văn bản với tài liệu Word.

## Bước 1: Thiết lập thư mục tài liệu
 Bắt đầu bằng cách thiết lập đường dẫn đến thư mục tài liệu của bạn. Thay thế`"YOUR DOCUMENT DIRECTORY"` với đường dẫn thực tế đến thư mục mà bạn muốn lưu tài liệu.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Bước 2: Tạo Tài liệu mới và DocumentBuilder
 Tạo một phiên bản mới của`Document` lớp học và một`DocumentBuilder`đối tượng làm việc với tài liệu.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Bước 3: Chèn và định cấu hình hình dạng biểu đồ
 Chèn hình dạng biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder` sự vật. Đặt loại và kích thước biểu đồ mong muốn.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## Bước 4: Thêm dữ liệu vào biểu đồ
Thêm dữ liệu vào chuỗi biểu đồ, bao gồm các giá trị ngày giờ.

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## Bước 5: Cấu hình trục
Định cấu hình trục X của biểu đồ để hiển thị các giá trị ngày giờ.

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## Bước 6: Lưu tài liệu
 Lưu tài liệu vào thư mục được chỉ định bằng cách sử dụng`Save` phương pháp. Cung cấp tên tệp mong muốn với phần mở rộng tệp thích hợp. Trong ví dụ này, chúng tôi lưu tài liệu dưới dạng "WorkingWithCharts.DateTimeValuesToAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Mã nguồn ví dụ cho Giá trị ngày giờ theo trục bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	// Đặt đơn vị chính thành một tuần và đơn vị nhỏ thành một ngày.
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

Mã ví dụ này tạo một tài liệu Word mới, chèn biểu đồ cột với các giá trị ngày giờ trên trục X và lưu tài liệu vào thư mục đã chỉ định.

## Phần kết luận
Trong hướng dẫn này, bạn đã học cách thêm các giá trị ngày giờ vào trục của biểu đồ bằng Aspose.Words for .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tạo biểu đồ, thêm giá trị ngày giờ vào chuỗi và đặt cấu hình trục để hiển thị chính xác giá trị ngày giờ. Aspose.Words for .NET cung cấp một bộ tính năng mạnh mẽ để Xử lý văn bản với các biểu đồ trong tài liệu Word, cho phép bạn trình bày và trực quan hóa dữ liệu với các giá trị ngày giờ một cách hiệu quả.

### Câu hỏi thường gặp

#### Q1. Tôi có thể thêm giá trị ngày giờ vào trục của biểu đồ bằng Aspose.Words cho .NET không?
Có, với Aspose.Words for .NET, bạn có thể thêm và hiển thị các giá trị ngày giờ trên trục của biểu đồ trong tài liệu Word. Aspose.Words cung cấp API và chức năng để hoạt động với nhiều loại biểu đồ khác nhau và tùy chỉnh giao diện của chúng, bao gồm cả việc xử lý các giá trị ngày giờ trên trục.

#### Q2. Làm cách nào để thêm giá trị ngày giờ vào chuỗi biểu đồ?
 Để thêm các giá trị ngày giờ vào chuỗi biểu đồ, bạn có thể sử dụng`Add`phương pháp của chuỗi biểu đồ. Cung cấp một mảng các giá trị ngày giờ dưới dạng dữ liệu danh mục (trục X), cùng với các giá trị chuỗi tương ứng. Điều này cho phép bạn vẽ các điểm dữ liệu với các giá trị ngày giờ trên biểu đồ.

#### Q3. Làm cách nào tôi có thể định cấu hình trục để hiển thị giá trị ngày giờ?
 Bạn có thể định cấu hình trục của biểu đồ để hiển thị các giá trị ngày giờ bằng cách đặt các thuộc tính thích hợp. Ví dụ: bạn có thể chỉ định giá trị tối thiểu và tối đa cho trục bằng cách sử dụng`Scaling.Minimum` Và`Scaling.Maximum` các thuộc tính tương ứng. Ngoài ra, bạn có thể đặt đơn vị chính và đơn vị phụ để xác định khoảng và dấu đánh dấu cho trục.
