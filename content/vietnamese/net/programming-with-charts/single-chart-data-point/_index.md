---
title: Tùy chỉnh một điểm dữ liệu biểu đồ trong biểu đồ
linktitle: Tùy chỉnh một điểm dữ liệu biểu đồ trong biểu đồ
second_title: API xử lý tài liệu Aspose.Words
description: Tìm hiểu cách tùy chỉnh một điểm dữ liệu trong biểu đồ bằng Aspose.Words for .NET.
type: docs
weight: 10
url: /vi/net/programming-with-charts/single-chart-data-point/
---

Hướng dẫn này giải thích cách sử dụng Aspose.Words cho .NET để tùy chỉnh một điểm dữ liệu trong biểu đồ. Mã nguồn được cung cấp trình bày cách tạo biểu đồ, truy cập các điểm dữ liệu cụ thể và sửa đổi thuộc tính của chúng.

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

 Tiếp theo, sử dụng`InsertChart` phương pháp của`DocumentBuilder` để chèn biểu đồ đường vào tài liệu.

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## Bước 3: Truy cập và tùy chỉnh điểm dữ liệu

 Để sửa đổi các điểm dữ liệu riêng lẻ, bạn cần truy cập vào`ChartDataPointCollection` của chuỗi và chọn điểm dữ liệu mong muốn bằng cách sử dụng chỉ mục.

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## Bước 4: Lưu tài liệu

 Cuối cùng, lưu tài liệu vào thư mục đã chỉ định bằng cách sử dụng lệnh`Save` phương pháp của`Document` sự vật.

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

Điều này hoàn tất việc triển khai tùy chỉnh một điểm dữ liệu trong biểu đồ bằng Aspose.Words for .NET.

### Mã nguồn ví dụ cho Điểm dữ liệu biểu đồ đơn bằng cách sử dụng Aspose.Words cho .NET 

```csharp
	// Đường dẫn đến thư mục tài liệu của bạn
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## Phần kết luận

Trong hướng dẫn này, bạn đã học cách tùy chỉnh một điểm dữ liệu trong biểu đồ bằng Aspose.Words cho .NET. Bằng cách làm theo hướng dẫn từng bước và sử dụng mã nguồn được cung cấp, bạn có thể tạo tài liệu mới, chèn biểu đồ đường, truy cập các điểm dữ liệu cụ thể trong chuỗi biểu đồ và sửa đổi thuộc tính của chúng để đạt được tùy chỉnh mong muốn.

Aspose.Words for .NET cung cấp các tính năng mạnh mẽ để thao tác biểu đồ trong tài liệu Word. Bằng cách truy cập các điểm dữ liệu riêng lẻ trong chuỗi biểu đồ, bạn có thể áp dụng các sửa đổi cụ thể để tùy chỉnh giao diện và hành vi của chúng. Điều này cho phép bạn làm nổi bật các điểm dữ liệu cụ thể, thay đổi ký hiệu điểm đánh dấu, điều chỉnh kích thước điểm đánh dấu, v.v. để nâng cao khả năng trình bày trực quan cho biểu đồ của bạn.

Việc tùy chỉnh các điểm dữ liệu riêng lẻ giúp bạn linh hoạt nhấn mạnh dữ liệu quan trọng hoặc làm nổi bật các xu hướng cụ thể trong biểu đồ của mình. Với Aspose.Words for .NET, bạn có thể dễ dàng truy cập và sửa đổi các điểm dữ liệu trong nhiều loại biểu đồ khác nhau, cho phép bạn tạo các biểu đồ giàu thông tin và hấp dẫn trực quan trong tài liệu Word của mình.

### Câu hỏi thường gặp

#### Q1. Tôi có thể tùy chỉnh nhiều điểm dữ liệu trong biểu đồ không?
 Có, bạn có thể tùy chỉnh nhiều điểm dữ liệu trong biểu đồ bằng Aspose.Words for .NET. Bằng cách truy cập vào`ChartDataPointCollection`của một chuỗi, bạn có thể chọn và sửa đổi nhiều điểm dữ liệu dựa trên chỉ mục của chúng. Sử dụng vòng lặp hoặc các bài tập riêng lẻ để sửa đổi các thuộc tính mong muốn cho từng điểm dữ liệu. Bằng cách này, bạn có thể áp dụng các tùy chỉnh khác nhau cho nhiều điểm dữ liệu trong cùng một biểu đồ.

#### Q2. Làm cách nào để thay đổi biểu tượng điểm đánh dấu cho điểm dữ liệu?
 Để thay đổi ký hiệu đánh dấu cho một điểm dữ liệu trong biểu đồ bằng Aspose.Words cho .NET, bạn cần truy cập vào`Marker` tài sản của`ChartDataPoint` đối tượng và thiết lập`Symbol` thuộc tính cho ký hiệu đánh dấu mong muốn. Ký hiệu điểm đánh dấu thể hiện hình dạng hoặc biểu tượng được sử dụng để thể hiện từng điểm dữ liệu trên biểu đồ. Bạn có thể chọn từ nhiều biểu tượng đánh dấu tích hợp khác nhau như hình tròn, hình vuông, hình thoi, hình tam giác, ngôi sao, v.v.

#### Q3. Tôi có thể điều chỉnh kích thước của điểm đánh dấu điểm dữ liệu không?
 Có, bạn có thể điều chỉnh kích thước của điểm đánh dấu điểm dữ liệu trong biểu đồ bằng Aspose.Words for .NET. Truy cập`Marker` tài sản của`ChartDataPoint` đối tượng và thiết lập`Size`thuộc tính theo kích thước điểm đánh dấu mong muốn. Kích thước của điểm đánh dấu thường được chỉ định theo điểm, trong đó giá trị lớn hơn biểu thị kích thước điểm đánh dấu lớn hơn. Việc điều chỉnh kích thước điểm đánh dấu cho phép bạn nhấn mạnh các điểm dữ liệu cụ thể hoặc phân biệt chúng dựa trên tầm quan trọng của chúng.

#### Q4. Tôi có thể sửa đổi những thuộc tính nào khác cho điểm dữ liệu?
Aspose.Words for .NET cung cấp một loạt thuộc tính mà bạn có thể sửa đổi cho một điểm dữ liệu trong biểu đồ. Một số thuộc tính thường được sửa đổi bao gồm ký hiệu điểm đánh dấu, kích thước điểm đánh dấu, màu điểm đánh dấu, khả năng hiển thị nhãn dữ liệu, vụ nổ, đảo ngược nếu âm, v.v. Các thuộc tính này cho phép bạn tùy chỉnh giao diện, hành vi và tính tương tác của từng điểm dữ liệu, cho phép bạn tạo biểu đồ phù hợp với yêu cầu cụ thể của mình.

#### Q5. Tôi có thể tùy chỉnh các điểm dữ liệu trong các loại biểu đồ khác không?
Có, bạn có thể tùy chỉnh các điểm dữ liệu trong nhiều loại biểu đồ khác nhau bằng Aspose.Words for .NET. Mặc dù hướng dẫn này trình bày cách tùy chỉnh các điểm dữ liệu trong biểu đồ đường, nhưng bạn có thể áp dụng các kỹ thuật tương tự cho các loại biểu đồ khác như biểu đồ cột, biểu đồ thanh, biểu đồ hình tròn, v.v. Quá trình này bao gồm việc truy cập chuỗi và điểm dữ liệu trong biểu đồ và sửa đổi các thuộc tính của chúng cho phù hợp.