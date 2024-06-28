---
title: Xác định thuộc tính trục XY trong biểu đồ
linktitle: Xác định thuộc tính trục XY trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách xác định thuộc tính trục XY trong biểu đồ bằng Aspose.Words for .NET. Các tùy chọn tùy chỉnh cho trục X và Y được thể hiện.
type: docs
weight: 10
url: /vi/net/programming-with-charts/define-xyaxis-properties/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để xác định các thuộc tính cho trục X và Y trong biểu đồ. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, thêm dữ liệu chuỗi và tùy chỉnh các thuộc tính trục.

## Bước 1: Thiết lập dự án

Đảm bảo rằng bạn có các điều kiện tiên quyết sau:

- Đã cài đặt thư viện Aspose.Words cho .NET. Bạn có thể tải xuống bằng cách sử dụng trình quản lý gói NuGet để cài đặt nó.
- Đường dẫn thư mục tài liệu nơi tài liệu đầu ra sẽ được lưu.

## Bước 2: Tạo một tài liệu mới và chèn biểu đồ.

 Tạo một cái mới`Document` đối tượng và một`DocumentBuilder` để xây dựng tài liệu.

```csharp
// Đường dẫn đến thư mục tài liệu của bạn
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Tiếp theo, chèn biểu đồ vào tài liệu bằng cách sử dụng`InsertChart` phương pháp của`DocumentBuilder`. Trong ví dụ này, chúng tôi sẽ chèn biểu đồ vùng.

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Thêm dữ liệu chuỗi vào biểu đồ

Thêm dữ liệu chuỗi vào biểu đồ. Trong ví dụ này, chúng tôi sẽ thêm năm điểm dữ liệu có ngày và giá trị tương ứng.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## Bước 4: Tùy chỉnh thuộc tính trục X và Y

 Để tùy chỉnh các thuộc tính của trục X và Y, hãy truy cập vào`ChartAxis` các đối tượng liên quan đến biểu đồ.

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

 Sửa đổi các thuộc tính của`xAxis` Và`yAxis`đối tượng để đặt các tùy chọn mong muốn cho trục X và Y. Trong ví dụ này, chúng tôi sẽ trình bày một số thuộc tính phổ biến có thể được tùy chỉnh.

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## Bước 5: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

Điều này hoàn tất việc triển khai xác định các thuộc tính trục XY trong biểu đồ bằng Aspose.Words for .NET.

### Mã nguồn mẫu cho Xác định thuộc tính XYAxis bằng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Chèn biểu đồ
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// Thay đổi trục X thành danh mục thay vì ngày, do đó tất cả các điểm sẽ được đặt với khoảng cách bằng nhau trên trục X.
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; //Được đo bằng đơn vị hiển thị của trục Y (hàng trăm).
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách xác định các thuộc tính cho trục X và Y trong biểu đồ bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tạo biểu đồ, thêm dữ liệu chuỗi và tùy chỉnh các thuộc tính trục để đáp ứng các yêu cầu cụ thể của mình. Aspose.Words for .NET cung cấp API toàn diện cho Xử lý văn bản với các biểu đồ trong tài liệu Word, cho phép bạn thao tác các khía cạnh khác nhau của biểu đồ, bao gồm cả các trục.

Bằng cách truy cập vào`ChartAxis` đối tượng được liên kết với biểu đồ, bạn có thể sửa đổi các thuộc tính như loại danh mục, đường chéo trục, dấu kiểm, vị trí nhãn, tỷ lệ, v.v. Tính linh hoạt này cho phép bạn điều chỉnh giao diện và hoạt động của các trục của biểu đồ để trình bày dữ liệu của bạn một cách hiệu quả.

Bằng cách sử dụng Aspose.Words cho .NET, bạn có thể tích hợp liền mạch khả năng tạo và tùy chỉnh biểu đồ vào các ứng dụng .NET của mình và tự động hóa việc tạo tài liệu có giao diện chuyên nghiệp với hình ảnh trực quan phong phú.

### Câu hỏi thường gặp

#### Q1. Aspose.Words cho .NET là gì?
Aspose.Words for .NET là một thư viện xử lý tài liệu mạnh mẽ cho phép các nhà phát triển tạo, thao tác và lưu tài liệu Word theo chương trình trong các ứng dụng .NET. Nó cung cấp nhiều tính năng cho Xử lý văn bản với các thành phần tài liệu, bao gồm cả biểu đồ.

#### Q2. Làm cách nào tôi có thể cài đặt Aspose.Words cho .NET?
Bạn có thể cài đặt Aspose.Words cho .NET bằng cách tải xuống bằng cách sử dụng trình quản lý gói NuGet trong Visual Studio. Chỉ cần tìm kiếm "Apose.Words" trong trình quản lý gói NuGet và cài đặt nó vào dự án của bạn.

#### Q3. Tôi có thể tùy chỉnh các khía cạnh khác của biểu đồ bằng Aspose.Words cho .NET không?
Có, Aspose.Words for .NET cung cấp các khả năng mở rộng để tùy chỉnh các khía cạnh khác nhau của biểu đồ. Ngoài việc xác định thuộc tính trục, bạn có thể sửa đổi loại biểu đồ, chuỗi dữ liệu, chú giải, tiêu đề, vùng biểu đồ, nhãn dữ liệu và nhiều thành phần khác của biểu đồ. API cung cấp khả năng kiểm soát chi tiết đối với giao diện và hành vi của biểu đồ.

#### Q4. Tôi có thể tạo các loại biểu đồ khác nhau bằng Aspose.Words cho .NET không?
 Có, Aspose.Words for .NET hỗ trợ nhiều loại biểu đồ, bao gồm vùng, thanh, đường, hình tròn, phân tán, v.v. Bạn có thể dùng`ChartType` liệt kê để chỉ định loại biểu đồ mong muốn khi chèn hình dạng biểu đồ vào tài liệu Word.

#### Q5. Tôi có thể lưu biểu đồ ở các định dạng khác nhau không?
Có, Aspose.Words for .NET cho phép bạn lưu tài liệu chứa biểu đồ ở nhiều định dạng khác nhau, chẳng hạn như DOCX, PDF, HTML, v.v. Bạn có thể chọn định dạng phù hợp dựa trên yêu cầu của mình và sử dụng`Save` phương pháp của`Document` đối tượng để lưu tài liệu.

#### Q6. Tôi có thể áp dụng những kỹ thuật này cho nhiều biểu đồ trong một tài liệu không?
 Có, bạn có thể áp dụng các kỹ thuật này cho nhiều biểu đồ trong tài liệu bằng cách lặp lại các bước cần thiết cho từng biểu đồ. Bạn có thể tạo riêng`Chart` Và`ChartAxis` đối tượng cho từng biểu đồ và tùy chỉnh thuộc tính của chúng cho phù hợp. Aspose.Words for .NET cung cấp hỗ trợ đầy đủ cho Xử lý từ với nhiều biểu đồ trong một tài liệu.